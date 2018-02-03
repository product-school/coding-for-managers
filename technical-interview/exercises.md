## Technical Interviews

Let's split up into teams of two if possible

There will be two phases to our interview: The question stage, and the architecture design stage

* Conceptual Questions

This is your opportunity to really shine as an engineer. Really a good programmer is not just someone who can write good code, but it's someone who can explain their _solution_ concisely, and with a logic that flows and is easy to understand. In the real world, startups and big companies will constantly spend resources (time + money) building something that they don't end up using. It's not just on the Product Managers to make all the decisions- a good programmer always has a "_why_" for what he is building, and will actively speak up if something is not feasible or does not deliver the user true value. 

* Architecture Overview

Together with your team member come up with a new exciting startup idea that is going to use the latest tech. You need to incorporate at least one third party API, and your solution must be "full stack" (involving at the least a frontend, server, and database). If you really are stuck on ideas check out this site: http://tiffzhang.com/startup/index.html?s=174598551673

You will need to draw your architecture diagram and explain the choices you made for the tech stack. 



## Adding a feature to your blog.

We're going to add some real functionality to the favoriting system

What is the broad overview of what we want to achieve with our persistent favorites?

* current user sees an empty star icon (if the current user hasn't favorited it yet) next to each post and a cumulative favorited count from all users

* see a full star icon if the current user has favorited it

What is the broad overview of how we might achieve this?

* when the user clicks on a star, an ajax request is made to the server

* the server receives the ajax request, creates a record of the favorite, noting both the primary key (id) of both the user and the post so that they can be linked together.

* a response is sent back to the client with data indicating the new favorite count for the post

* in the success handler for the AJAX call we update the UI with the favorite count and a new full star icon

So what do we need?

1. A [join table](https://en.wikipedia.org/wiki/Associative_entity) and model for favorites

You should be presented with a migration file like so:
```rb
class CreateFavorites < ActiveRecord::Migration
  def change
    create_table :favorites do |t|
      t.integer :user_id
      t.integer :post_id

      t.timestamps null: false
    end
  end
end
```

2. Some model logic to record / count favorites

Inside of your `favorite.rb`, create a class-level (`def self.method_name`) method named `mark_favorite` that takes two arguments: `post_id` and `user_id`. The first order of business is to create a database record with those two pieces of information. We can do that with `Favorite.create(user_id: user_id, post_id: post_id)`. *This will ensure that each favorite record will have a `post_id` and a `user_id`, linking the primary id's together*. Next, we want to count all the favorites for the relevant post. We can do that by querying all the favorite entries using the `where` method with the post's id and asking for the count. That should be one line and should be the last line in the method - therefore it will also be the return value, handing off the cumulative favorite count to the controller.


3. An API controller

Create a new controller called `favorites_controller.rb` in your `api/v1` directory.
The controller should call the `mark_favorite` method on the `Favorite` class, pass in the `current_user`'s id and the id of the post from the `params` hash and render a JSON count of total favorites for the post back to the client.

4. A route

In your `routes.rb` file, create a new custom route for the favorite API. It should follow the same form as the weather route, however this will be a `post` request instead of a `get` request.


5. Migrate and add Rails model associations

*With these associations, you will now have access to a method called `favorites` on users and posts. With this, you could create a favorites section for each of your users to record / show their favorite items. You could also potentially display a list of users who have favorited a speicific post.*

6. A data property on each post in our HTML to help us know each post's id

HTML5 brought along with it an amazing feature - data properties on HTML elements. That means we can attach data onto any elements by specifying an HTML element property like so with a key - value pair: `data-<keyname>="<value>"`. In our case, we want to add a new `id` data property named `data-id` (`id` is the keyname) onto each favorite icon div that the user will be clicking on. The value will be each post's `id`, which we can get by accessing the post's `id` property like so: `post.id`. This will let our click handler identify which post our user has clicked as a favorite. Add this new HTML element property onto the element in `index.html.erb` that has the `glyphicon glyphicon-star-empty favorite` class.


7. A counter element in our HTML

In the same `<td>` as our star icon and just below it. We can use the `favorites` convenience method on our `post` object because we told Rails about the association between posts and favorites when we said `has_many :favorites` in our Post model. Then we just need to count the favorites.

8. An AJAX call inside of our click listener
Now that we have a data property that lets us know the id of each post, we can grab that off of the click target (`this`) by accessing the dataset property and then asking for the `id` key. Inside of your `$(".favorite").click` handler, `console.log` the data property of `this` to make sure you have the correct id of each post.


Next, intead of console.logging, we want to pass that piece of information to our server using an AJAX call. Create a new function called `markFavorite` that takes one argument: `postID`. Inside of the function, you should send a `"POST"` request to `/api/v1/mark_favorite`.  You can follow the same AJAX request format found in your `home` view's `index.html.erb` for the weather request, but add in two new properties and values: `method: "POST",` and a data object that has one key and one value: `data: { post_id: postID },`. Make sure you DO NOT have the property `contentType: 'json'`. In the AJAX `success` method, which will take one argument, `response`, you should first put a `console.log(response)` to make sure everthing is working properly.

9. At this point you should have a working solution. The only thing left to do is make the star stay filled in if a user has already liked it. You'll notice that if you navigate away and back tot he index page the stars don't persist. How can we fix this? By using the `favorites` method on the user and seeing if one of their favorites matches the id of the post. We'll need to add some conditional logic into the `index.html.erb`. If `post.favorites.find_by(user_id: current_user.id)` is true, we should show the `glyphicon-star`, otherwise we should show the `glyphicon-star-empty`.


EXTRA CREDIT:
How can we control for one star per user per post?
How can we allow a user to retract his/her star vote?
How can we create a favorite posts section for each user?
