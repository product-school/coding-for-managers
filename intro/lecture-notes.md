# <img src="https://cloud.githubusercontent.com/assets/8397980/19818474/bd21af4c-9d04-11e6-8df6-1ed154718dce.png" height="60">

# Hello World!

The goal of this lecture is to give you a roadmap for the course, teach you HTML, introduce you to CSS and to basic concepts of coding such as Graphical User Interface, Integrated Development Environment and Command Line Interface.

## What you will learn in this course
* What is a Graphical User Interface (GUI)
* Use an IDE such as Cloud 9
* Use basic commands of the Terminal
* Use Development tool
* Structure a webpage with HTML
  * Create a list
  * Embed an image into your webpage
  * Create a form
  * Create a navigation menu


## Introductions
### Our Project
Our project throughout the whole program will be to build a  blog where you'll be able to write articles, have an about page, sign in and sign up. Click on the link below to have an overview of what it will look like.
* [What are we going to build?](http://p-school-blog.herokuapp.com)

### Best practices
Some good rules of thumbs to remember during the class are:

**Google when you don't know**
No software engineers have everything in mind when they are coding. Google is a very powerful resource to find what you are looking for.

**Read the lectures notes before class**
Learning coding can be pretty hard at the beginning especially if you have never been exposed to it. Read the lectures notes before each classes will help you understand faster key concepts that will be taught in class.

**Ask as many questions as you like**
Don't be afraid to ask questions during class. If you don't understand something, you will most likely not be alone in that case. Don't hesitate to raise you hand and ask.


### Initial Setup
You will need two tools to get set up for the class. Make sure to create an account on Cloud 9 and Github before class. You should receive an invite from your Program Manager to both these tools.
* [Cloud9](https://c9.io)
* [Github](https://github.com)

### IDE/CLI
An Integrated Development Environment (IDE) is program that combines several tools a software developer needs into one place. An IDE usually acts as a text editor, a debugger and a compiler. The IDE we are going to use in this class is called Cloud 9. With this tool you will be able to write code and directly execute it online without ever putting anything on your own computer.

* Create our first workspace in Cloud9
    * HTML5
    * GUI
    * IDE
    * CLI

At the bottom of your workspace in Cloud 9, you will see something called the command line interface (CLI) or console or shell. Typically, this application will let you access, create, delete files and folders without using the usual graphical interface of your computer. It is very useful once you start creating complex applications because you will need to have all your work in local files and still be able to share it with your team.

* Shell Commands ([POSIX](http://pubs.opengroup.org/onlinepubs/9699919799/)/[UNIX](https://upload.wikimedia.org/wikipedia/commons/c/cd/Unix_timeline.en.svg))
    * `ls` (`-t`, `-a`)
    * `pwd`
    * `man`
    * `mkdir`
    * `cd`
    * `touch`
    * `mv`
    * `rm`

*> Exercise: follow along with me to learn some command line basics*

### HTML

Hyper-text Markup Language represents the frame or skeleton of any web page that you see on the Internet. Any front-end or full-stack developer will be working with it daily. The basic concepts of HTML can be learned quickly and you’ll have time to deepen your knowledge of specific attributes, tricks, and tools over time.

#### HTML page structure, head & body

Let's create an index HTML file: `$ touch index.html`

Tags are the foundation of HTML. They usually start with `<name of the tag>` and end with `</name of the tag>`. You will be able to put text within the opening and closing tag. This is how you will structure your webpage with HTML. Here is an example of some basic tags:
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    Content Here
  </body>
</html>
```
[HTML body tags full list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

Commonly Used Tags:

- Headings: `<h1> - <h6> <h1>Hello World</h1>`
- Span: `<span>Copy text</span>`
- **Div**: `<div> [content to be placed inside] </div>`
  - inspect FB page with Chrome Dev Tools (cmd + alt + i)

##### Dev Tool
Now that you have a first experience with Chrome dev tool let's explain a little bit what it is. Dev tool is something in your web browser where you will be able to inspect elements or write directly some code on a webpage. This is very useful and powerful as it can help you writing or testing your code.

*> Exercise: Change the title. Then add a heading of whatever size you want within the body and put one of the words into a span*

Let's create a page directory: `$ mkdir pages`

#### Lists:
Lists are often used in HTML. For example, you can easily create navigation menu thanks to lists. There are two types of lists:

- Unordered list: `<ul> [list items] </ul>`
- List item: `<li> item </li>`

Let's create a menu file: `$ touch pages/products.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Products</title>
  </head>
  <body>
    <ul>
      <li>Burrito</li>
      <li>Dumplings</li>
      <li>Spaghetti</li>
    </ul>
  </body>
</html>
```
*Exercise: add another product to the list*


#### Form:
Forms are used everywhere in the internet. The most common ones are contact forms. Here is how to build them:

- Label `<label>`
- Input `<input>`
- Horizontal Rule (aka: horizontal divider line): `<hr>`
- Line break: `<br>`

Let's create a contact us file: `$ touch pages/contact_us.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Contact Us</title>
  </head>
  <body>
    <form>
      <div>
        <label>Email</label> <input required="required" type="email"/>
      </div>
      <div>
        <label>Image</label> <input required="false" type="file"/>
      </div>
      <div>
        <label>Compress Photo?</label>
        <input type="checkbox" value="1"/>
      </div>
      <br>
      <div>
        <label>Category</label>
        <select>
          <option value="1">Compliment</option>
          <option value="2">Complaint</option>
          <option value="3">General Inquiry</option>
        </select>
      </div>
      <hr>
      <div>
        <input type="submit" value="Submit"/>
      </div>
    </form>
  </body>
</html>
```
*Exercise: add another dropdown menu item and another horizontal rule*

- Common form text field types: text, email, password, search, URL
- [Built-in validators](http://www.the-art-of-web.com/html/html5-form-validation/)
- Form field types without text field ‘input’: checkbox, file, radio, number range
- Form buttons: button, reset, submit [W3 Schools](http://www.w3schools.com/tags/att_button_type.asp)

#### Image:
If you want to have a nice webpage, you will probably need to add some images to it. One thing to know about image is that it is a self closing tag. Here is how to embed an image to your website:
- Image: `<img src=”file-path-or-URL” alt=”alternative title”/>`

Let's create an about file: `$ touch pages/about.html`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>About</title>
  </head>
  <body>
    <div class="image_container">
      <img src="https://imgs.xkcd.com/comics/code_quality_2.png"/>
    </div>
  </body>
</html>
```

*Exercise: add an image of your choosing*


#### Navigation:
In order for your user to have a smooth navigation into your website, you will need to add a navigation menu. Here is a simple way to make one:

- Nav: `<nav> [nav items in here] </nav>`
- Links: `<a href="URL">Link title</a>`

```html
<nav>
  <a href="index.html">Home</a> |
  <a href="pages/about.html">About</a> |
  <a href="pages/products.html">Products</a> |
  <a href="pages/contact_us.html">Contact Us</a>
</nav>
```
*Exercise: add this to each page at the top of the body and test it out. Something is broken - why?*

**Resources:**

- For more information on CSS selectors: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference

- For an example of a styleguide: https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/CSS_style_guide

**Other Resource for Practice**

- https://www.codecademy.com/
