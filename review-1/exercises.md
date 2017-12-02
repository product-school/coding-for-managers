# Exercise

We've covered a lot of front-end concepts in these firsts courses. Let's put all together by building a simple landing page for our project. We'll do something called **pair programming** today. Team up with a partner sitting next to you to go through today's exercises. Don't be shy!

## Set up
First, let's create a new Cloud 9 project, that we will call `landing-page`. Once everything is loaded, you can remove all the different folders and files that are preloaded so that you can start from scratch.

### Create a `landing-page` folder
Once everything is removed, go on your console and create a `landing-page` directory. This is where we will build our landing page project.

**Hint:** Use command the command line

**Reminder:**
Create a folder: `$ mkdir name_of_directory`


### Create an `img` folder
Within your `landing-page` folder, we need now to have an `img` folder to store the image we are going to use as background.

**Hint:** You need first to go inside your `landing-page` directory before creating the `img` directory

**Reminder:**
Move inside a folder: `$ cd name_of_directory`
Move outside a folder: `$ cd ..`


### Create an `index.html` file
Now we need to create our HTML file where we will write our code. Create a file called `index.html`.

**Hint:** Careful, this is a file and not a folder

**Reminder:**
Create a file: `$ touch name_of_file.extension`
Remove file: `$ rm name_of_file.extension`
Move a file to another place: `mv name_of_file path_of_another_directory/name_of_file.extension`

### Create a `style.css` file
Now we need to create our style sheet, to be able to have a nice looking landing page! Create a `style.css`file.

##  Writing HTML
Congrats! Everything is set up now. You can actually start coding. First, we need to build the skeleton of our webpage. For our landing page, we will need:
- A header/title section where we'll have a background image and a title
- An About Me section so that people will know a little more about you.
- A Contact section so that people can reach out to you
- A Footer to put copyrights / social media links / etc.

First, let's set up our page with the basic HTML tags

### Basic tags
#### DOCTYPE HTML
First you need to tell the browser that your file is of type HTML.

**Hint:** Check the very first self closing tag of every html page (you can go on any website and open the web console)

#### html tags
Now that we have our document specified as HTML, we need to put our html tags. Put an opening and closing html tags. We'll put the our code inside those tags.

**Hint:** HTML tags look like this `<html></html>`

#### Head tags
We need to set up our **head tags**. Inside those head tags we want our landing to have a **title**.

**Reminders:**
```html
<html>
  <head>
    <title>Title of your webpage</title>
  </head>
</html>
```
#### Body tags
Now that our webpage has a title, we need to define the body of our webpage. Put body tags after your closing `</head>` tag.

### Title/Header section
Let's create a nice header/title for our landing page.

### Background image
After our opening `<body>` tag, let's add a `<div></div>` tags with a class of `background-image`. Everything that we'll need for our header will be written inside those tags.

**Reminder:**
To add a class: `<div class="name-of-your-class"></div>`

#### Navigation bar
We want a navigation bar so that users can click and be redirected to the corresponding sections. Let's build a Nav Bar. Give it a class of `navigation-bar`

**Hint:**
Nav tags: `<nav></nav>`

Inside this Nav Bar, we'll need to write an **unordered list** with a class of `navigation-items`. Within it create **list items** that users can click on. Give respectively an id of:
- about-list-item
- contact-list-item
- blog-list-item

**Hint:**
Unordered List: `<ul></ul>`
List items: `<li></li>`
(Careful: List items need to always be inside an ordered or unordered list)
Add an id: `<div id="name-of-id"></div>`

Those **list items** should scroll the user to the corresponding section of the page. To do this, we need to add **anchor** tags to our menu items.

**Hint:**
Anchor tags: `<a href="link_to_redirect"></a>`
(To scroll the user to a section of your html page, you just need to use the hash/pound character "#name_of_the_id_element_you_want_your_link_to_redirect" inside your href attribute)
You can use href="#top" or the empty fragment href="#" to link to the top of the current page.

#### Welcome Title
Create another `<div></div>`. We are going to put our welcome title inside those divs. Give it a class of `first-section`.

Write a title saying : "Hi, I'm {{Your Name}}" with a class of `title-1`
Write a subtitle saying: "Welcome to my website" with a class of `title-2`

**Hints:**
h1 tags : `<h1></h1>`
h2 tags : `<h2></h2>`
h3 tags : `<h3></h3>`
h4 tags : `<h1></h1>`
h5 tags : `<h5></h5>`


### About Me
Good Job! You have a written a nice header! Now let's make an About me section. Let's create 2 other `<div></div>` where we'll put all our About Me content. The first one will have a class of `container`, the second one will be nested within our container and have a class of `second-section`

#### Title
Create a `<div></div>` and give it the same id that you put in your **about Anchor tag**.
Create a title called: "About Me" with a class of `about-title`

**Hint:**
h2 tags : `<h2></h2>`
id attribute: `<h2 id="your-id"></h2>`
If you want your `<a>` to redirect to your `<h2>` section, href attribute must target the `<h2>` id.
Ex:
```html
  <a href="#your-id">This link will scroll to HELLO WORLD</a>
  <h2 id="your-id">HELLO WORLD</h2>
```

#### Skills section
Let's make 2 other `<div></div>`. The first will wrap both Skills and Passion section and the second one  will only wrap our Skills section. Give the first div a class of `skills-interests-container` and the second one a class of `skills`

Inside that:
- create a title: "My Skills" with a class of `skills-title`
- create a list of your skills with a class of `skills-list`

**Hints:**
Use `<h3></h3>` for your title
Use `<ul></ul>` for your list
Don't forget `<li></li>` inside your unordered list.

#### interests section
We want to also show our interests in our website. Let's do the exact same as we did for our skills but replace by our interests. Replace `skills`, `skills-title` & `skills-list` by `interests`, `interests-title` and `interests-list`


### Contact Form
Great! We have our About Me written. Now what if someone would to contact you? We need a form to handle that!

First, let's put an `<hr></hr>` to separate our Contact Section from our About me.
Then let's create a `<div></div>` where we'll put our form and give this div an id of `contact` (if our put "#contact" in your href attribute of your Contact anchor tag)

#### Title

Create a title for your section called: "Contact Me" with the class of `contact-title`

#### Form
Now we need to create an actual form. Follow those steps

1. Create a `<form></form>` with an id of `contact_me`
2. Inside it create a first `<div></div>`
3. Inside it create an `<input/>` and give it the following attributes:
  - required attribute of `required`
  - type attribute of `text`
  - Value attribute of `Name`

4. Outside of the first div, create a second `<div></div>`
5. Inside it create an `<input/>` and give it the following attributes:
  - required attribute of `required`
  - type attribute of `email`
  - Value attribute of `Email`

5. Outside of the second div, create a third `<div></div>`
6. Inside it create an `<textarea></textarea>`
7. Outside of the third div, create a fourth and final `<div></div>`
8. Inside it create an `<input/>` with a class of `submit-button` and give it the following attributes:
  - required attribute of `required`
  - type attribute of `submit`
  - Value attribute of `Submit`

### Footer
We are almost there! We just need to put a footer now and our skeleton will be done.

Create a `<footer></footer>` and a `<div></div>` with a class of `copyright` within it.

Inside the div, create `<p></p>`. You will write something like this in it: Copyright (c) 2017 Copyright {Your Name} All Rights Reserved.

## Style your page
Great! Our HTML is written but our page is a little boring, we need to style it!
Let's first link our style sheet to our HTML page.

Inside your `<head></head>` link your `style.css` file.

**Reminder:***

```html
  <link rel="stylesheet" href="style.css">
```

We also need to set up basic styling as follow:
- Default margin for every element must be 0
- Default link shouldn't have text-decoration and be white.

**Hint:**
Select all elements: `* { property-1: value; }`
Select anchor elements: `a { propert-1: value; }`

### Style background image
Let's first put a background image for our header. Download the [image](img) and put in your `img` folder in your C9 project.

target the `background-image` class and give it the following properties:
- background-image: url("img/generic_background.jpg");
- background-repeat: no-repeat;
- background-position: center;
- background-size: cover;


### Style Nav bar
Now that we have our Background Image set, we should do something about our Navigation bar.

Target the `navigation-bar` class and give it the following properties:
- background-color: rgba(0,0,0, 0.01);
- display:flex;
- justify-content: flex-end;
- font-size: 20px;
- padding-right: 30px;
- padding-left: 30px;


Our list items appear vertically and with those bullet points in front of them. Let's fix this

Target the `navigation-items` class and give it the following properties:

- list-style: none;
- display:flex;
- flex-direction: row;

We have now our list items display in row but they are all stuck together.

Target `about-list-item, contact-list-item, blog-list-item` ids and give them 10px margin.

As you can see our header all squished on the top of your page.

Target `first_section` class and give it the following properties:
- display:flex;
- flex-direction: column;
- align-items: center;
- justify-content: center;
- height:80vh;

Let's style our titles a little bit. Let's do the following:
- Give both `title-1` and `title-2` classes a margin of 10px and color of white
- Give `title-1` a font-size of 60px
- Give `title-2` a font-size of 30px

### Style Skills and Passion Section
Our header looks great! Let's tackle our About section.

First, our font color.

Target `about-title, li, h3` elements and give them the color of black

We need to give a bigger height for our second section.

Target `second-section` class and give it a height of 60vh

Our "About Me" title needs to be taken care of. Target `about` id and give it the following properties:

- display:flex;
- justify-content: center;
- margin:20px;
- padding-bottom: 40px;
- font-size:25px;

Let's now focus on our skills and interests.

Target the `h3` elements and give them the following properties:
- display:flex;
- justify-content: center;
- margin:10px;

We want to put both our skills and interests div at the same level.

Target `skills_interests_container` class and give it the following properties:
- display: flex;
- flex-direction: row;
- justify-content: center;

Let's style our divs. Target `skills` and `interests` classes and give them the following properties:
- border: 2px solid black;
- border-radius: 5px;
- font-size:20px;

Our divs are stuck to each other, let's fix this but giving `skills` a 100px right margin.

Finally our divs a little too small. Target `skills-list` and `interests-list` classes and give them the following padding:
- padding: 20px 70px 30px 70px;


### Style Form
Our form is not very sexy right now. If we want someone to actually contact us we need to fix this.

Let's start by separating our About section and Contact section by style `hr` element. Target `hr` and give it the following properties:

- margin:20px auto 70px;
- width: 60%;

Let's now style our title. Target `contact-title` class and give it the following properties:
- color:black;
- font-size: 35px;
- margin:20px;
- display: flex;
- justify-content: center;


Now let's style our form itself. First target `contact_me` id and give it the following properties:
- color:black;
- display:flex;
- align-items: center;
- flex-direction: column;
- margin: 20px;
- margin-left: 80px;

Let's now give a little more space in between each fields. Target each `div` inside `contact_me` id and give them the following properties:
- margin:20px;
- width:40%;


We need to style our `input` elements. Target them inside `contact_me` and give them the following properties:
- width: 80%;
- height:30px;
- font-size: 15px;
- border:1px solid grey;
- border-radius: 3px;

We need to style our `textarea` now. Let's target it inside `contact_me` and give it the following properties:

- width: 80%;
- height: 100px;
- font-size: 15px;
- border: 1px solid grey;
- border-radius:3px;

Finally let's style our button. Target `submit-button`and give it the following properties:

- background-color:#17a5e8;
- color:white;



### Style Footer
Almost done! We now need a final thing: Styling our footer

Target your `footer` element and give it the following properties:
- background-color: lightgrey;
- margin-top: 10px;
- padding: 10px;
- text-align: center;


## Homework

HOORAY! You built a nice landing page for your blog!

But there are few things you need to fix. One of them is that your site is not responsive.

Using Media Queries, style your landing page so that it looks great on any device.

Don't forget to use Developer tools in your browser to help you with sizing. 
