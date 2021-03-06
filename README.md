# facu-training

## Study plan

1. [WEB 101](#web-101)
2. [Front End Introduction](#front-end)
3. [GIT](#git)
4. [HTML](#html)
5. [CSS](#css)
6. [Boolean Algebra](#boolean-algebra)
7. [Programming 101](#programming-101)
8. [JS](#js)
9. [Front End Frameworks](#front-end-frameworks)
10. [Final Project](#final-project)

## WEB 101

Each computer connected to the internet has an unique IP address. (xxx.xxx.xxx.xxxx).
To communicate between each other, the computers uses the TCP/IP protocol. The messages must be translated from alphabetic text into electronic signals, transmitted over the internet.
It's hard to remember each computer's address, so the DNS (Domain Name Service) helps us here. It's a distributed database which keeps track of computer's names and their corresponding IP addresses on the Internet. (that's why you can type google.com and see the webpage).

### HTTP and the World Wide Web

The protocol that makes the web work is Hypertext Transfer Protocol. Is the protocol used by servers and web browsers use to communicate with each other over the Internet.
This is what happens when you request a webpage with your browser:

1. If the URL contains a domain name, the browser first connects to a domain name server and retrieves the corresponding IP address for the web server.
2. The web browser connects to the web server and sends an HTTP request (via the protocol stack) for the desired web page.
3. The web server receives the request and checks for the desired page. If the page exists, the web server sends it. If the server cannot find the requested page, it will send an HTTP 404 error message. (404 means 'Page Not Found' as anyone who has surfed the web probably knows.)
4. The web browser receives the page back and the connection is closed.
5. The browser then parses through the page and looks for other page elements it needs to complete the web page. These usually include images, applets, etc.
6. For each element needed, the browser makes additional connections and HTTP requests to the server for each element.
7. When the browser has finished loading all images, applets, etc. the page will be completely loaded in the browser window.

These two concepts are important: client and server. But they are quite simple as well, they're both computers connected to the internet.

[SOURCE](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm#:~:text=The%20web%20browser%20connects%20to,an%20HTTP%20404%20error%20message.)

## Front End vs Back End

Front End and Back End are the two most popular terms used in web development.

### Front End

Is the part of the website that the user interacts with directly. It's executed on the `client side`, that means, it's executed on the user's pc (more specifically in the web browser). Buttons, Text, Links, Images, all that you can see on your web browser, is front end development.

#### Technologies used in FE development

The three most important technologies are: HTML, CSS and Javascript.

#### Front End Javascript Frameworks

The most popular are: React, Angular and VueJS.

### Back End

It's the server-side of the website. It's the part of the website that the user can't interact directly. It stores the data in the databases and responds to requests from the front end. This is NOT executed on the browser, it's hosted on a web provider. The front end interacts with the back end via internet.

#### Technologies used in BE development

Python, GoLang, Java, C#, Ruby, Javascript (with nodejs) and many more.

#### Back End Frameworks

For Python: Django, Flask
For Javascript: Express, Deno
For Ruby: Rails
For Java: Spring
For C#: .NET

[SOURCE](https://www.geeksforgeeks.org/frontend-vs-backend/)

## GIT

Free and open source distributed version control system. Is the software that most developers/projects uses to collaborate between team members and share their code. It allow us to track changes in your application across different users and different computers.

### Repository

Tracks and saves the history of all changes made to the files in a Git project. You can think of it as a supercharged folder. You can sync your local git repositories with remotes like Github, Gitlab or Bitbucket.

To initialize a repository, inside a folder, open a terminal and type

    git init

### Commit

A commit is a snapshot of your code at particular time, which we are saving to the COMMIT HISTORY of our repository. Only the files added to the stagging area will be commited (added to the commit history).

Add files to stagging

    git add file1 # it adds only one file
    git add file1 file2 file3 # adds multiple files
    git add . # adds all the files in the current folder

Commit to the history

    git commit -m "Adds my awesome feature!" # commits a snapshot of your code with a particular message

### Git Status

It's used to check the status of your repository. It tells you which files are untracked (new files), which files are modified, and which files are in the stagging area (ready to commit).

    git status

### Commit History

To see a list of the commits made to the repository

    git log

Jump to a specific version of your code

    git checkout <commit-hash> # you can grab the commit hash from the git log command output.

### Branches

A branch it's like a timeline of your repository. You can have multiple branches with different versions of your project code and they can be tracked in paralllel. This allows us to make changes in your code, without affecting our main timeline or production code. (the master or main branch). If we decide that our code in the branch is production ready, we can MERGE that branch into the main branch (or any other branch).

To create a new branch:

    git branch <new-branch-name>

Note that the branch that you create, will have all the commits added to the current branch you're in.

To switch to another branch:

    git checkout <branch-name>

Great! now you have your main branch, and your specific feature branch that you want to integrate to the main timeline of the code (production).
To do so, we use merge.

    git merge <source-branch-name>

Note that you're merging the source branch into the current branch that you're right now.

### Remotes

Right now, we're only working on our local machine. But what if we want to share our code? Thats when we need git remotes.

For this course, we'll use GitHub.

To sync your local repository to a remote:

    git remote add origin <repository>
    git branch -M main
    git push -u origin main

By default, Git uses master as the main branch name, but that can be confused with slavery (master/slave) and the new term main was adopted by the community. That's why in the second command we're renaming the master branch.

To fetch all the new branches that are on the remote:

    git fetch

To push your changes to a remote branch

    git push

To update your branch with the remote code

    git pull

A real world scenario: when I recieve a task to implement a new feature I do the following:

1. Create a feature branch from main.
2. Work on the code.
3. Add the changes to the stagging area.
4. Commit the snapshot into the history.
5. Push my local branch into the remote repository.
6. Open a merge request in the remote repository.
7. Merge my new changes into the master branch.

This, on git commands would look like this:

    git branch my-new-awesome-feature
    git add .
    git commit -m "Adds my new awesome feature"
    git push origin my-new-awesome-feature

Once it's pushed, you can use Github to open a merge request and review the changes that will be added to the main branch.

[SOURCE](https://www.youtube.com/watch?v=USjZcfj8yxE)

## HTML

It's the most basic building block of the Web. It defines the meaning and the structure of a web content.
HTML uses markup (tags) to annotate text, images, and other content for display in a Web browser.
An HTML element is represented with `<tag-name>`.

Basic structure of an HTML Document

    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8>
            <title>My awesome webpage!</title>
        </head>
        <body>
            <h1>Welcome to my page!</h1>
        </body>
    </html>

1. `<!DOCTYPE html>` instructs the browser that you're using the last version of HTML.
2. `<html>` the html element wraps all the content of the entire page (root element).
3. `<head>` acts as a container for all the metadata of the page (stuff that won't appear on the page content but it will affect how it works).
4. `<title>` the title of the page that will be displayed on the browser.
5. `<body>` this contains the content that will be visible and rendered by the browser.

### Typography

Headings: h1, h2, h3, h4, h5, h6
Paragraphs: p
Lists: ul (unordered list), ol (ordered list).
List Items: li

### Links

    <a href="http://google.com">Google it motherfucker!</a>

HTML elements sometimes can accept attributes like in this case the href which is instructing the link to where it should lead when clicked.

### Images

    <img src="my-penis.jpg" alt="It's a huge cock!">

Note that src and alt are attributes too.

### Tables

    <table>
        <thead>
            <tr>
                <th>Product Name</th>
                <th>Price</th>
                <th>Stock</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Switch</td>
                <td>80000</td>
                <td>3</td>
            </tr>
            <tr>
                <td>Galaxy S22</td>
                <td>200000</td>
                <td>9</td>
            </tr>
        </tbody>
    </table>

### Excercise: Create your fake company!

Create a HTML page that includes:

1. A title.
2. An image representing your company.
3. A paragraph about your company and what you do.
4. A link that redirects you to another page which contains a table of the employees of your company.

Hint: with the href attribute of the `<a>` element, you can also reference another html page.

The columns for the table should be: Employee Name, Role, Seniority (Junior, Semi-senior, Senior) and salary. Include at least 3 employees.

### More HTML knowledge

Read the following guides:

[ATTRIBUTES](https://www.w3schools.com/html/html_attributes.asp)

[TEXT FORMATTING](https://www.w3schools.com/html/html_formatting.asp)

[COMMENTS](https://www.w3schools.com/html/html_comments.asp)

[HTML BLOCK & INLINE](https://www.w3schools.com/html/html_blocks.asp)

[IFRAMES](https://www.w3schools.com/html/html_iframe.asp)

[ENTITIES](https://www.w3schools.com/html/html_entities.asp)

Notes:

1. We'll expand on HTML BLOCK & INLINE elements when we learn CSS, but this is a good start.
2. The entities page it's just for reference, you don't have to know all of them.

### Excercise: Practice your new HTML superpowers

Create a HTML document with the following:

1. A `lang` attribute on the `<html>` root element with the value `'en-US'`
2. Create a list `<ul>` with the attributes that you've learned.
3. For each list item, add a `title` attribute with the same value that's inside the item. This will create a tooltip when you hover over the item.
4. Add some style to your page using text formatting tags.

### Semantic HTML

Read [HTML5 SEMANTICS](https://www.w3schools.com/html/html5_semantic_elements.asp) to learn about the semantic structure of an HTML document.

### Exercise: Give your HTML document better semantics

1. Add a `<header>` element for your document.
2. Inside the `<header>`, put a `<nav>` element with an `<ul>` and `<li><a>Link<a/></li>` for each different page of your website. (right now you have About and Staff, try adding a third one called `"Contact"`, we'll fill this one later).
3. Add the title of your site at the top of your pages with a `<h1>` tag, then change your existing `<h1>`'s to `<h2>`'s.
4. Wrap the different sections of your site with `<section id="section-name">` elements. (wrap your `<h2>` and your `<p>` inside a `<section id="section-name">` for each section of your website)
5. In the main page, add a new section below `"About Us"`, named `"Our Mission"` and fill it with the content you want.
6. Add a `<footer>` to your website with your copyright and the address of your company. Remember to use the `<address>` element.

### HTML Forms

Read through the full section HTML Forms in the [w3schools page](https://www.w3schools.com/html/html_forms.asp).
Don't pay too much attention to the action attribute on the form, we'll handle this later. Just learn the structure of a form on HTML.

### Exercise: Fill your contact form

Remember the Contact page that we left blank? Fill it with a contact form.

1. name
2. email
3. phone
4. `<select>` with different reasons: (techical assistance, sales, other)
5. two radio buttons with the following labels: (client, not client)
6. text area for the comment
7. submit button

## CSS

### CSS Knowledge

## Knowledge !

[Syntax](https://www.w3schools.com/css/css_syntax.asp)

[CSS Selectors](https://www.w3schools.com/css/css_selectors.asp)

[Specifity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)

[The Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

[CSS Sizing](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS)

[CSS Display](https://www.w3schools.com/css/css_display_visibility.asp)

[CSS Positioning](https://www.w3schools.com/css/css_positioning.asp)

[CSS Positioning 2](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)

[Pseudo Classes](https://www.w3schools.com/css/css_pseudo_classes.asp)

[Pseudo Elements](https://www.w3schools.com/css/css_pseudo_elements.asp)

[Z-Index](https://www.w3schools.com/css/css_z-index.asp)

[Inline-Block](https://www.w3schools.com/css/css_inline-block.asp)

[CSS Units](https://www.w3schools.com/css/css_units.asp) (most used: px, em, rem, %, vh, vw)

[CSS Layout Introduction](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)

[Normal Flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)

[Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

[Flexbox 2](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

[Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids)

[CSS Media Queries](https://www.youtube.com/watch?v=yU7jJ3NbPdA)

[Responsive Design](https://www.youtube.com/watch?v=2zypRlzIcHc)

[CSS Colors](https://www.w3schools.com/css/css_colors.asp)

[CSS Backgrounds](https://www.w3schools.com/css/css_background.asp)

[CSS Text](https://www.w3schools.com/css/css_text.asp) (read all the subtopics; alignment, decoration, transformation, spacing and shadow)

[CSS Max Width](https://www.w3schools.com/css/css_max-width.asp)

## Exercise

Add a stylesheet to your project and use it on all your pages. [How To](https://www.w3schools.com/css/css_howto.asp) (please use external CSS).

Style your Header component. Create a selector (can be an ID or class) to target the header of your website.

Tips:

1. Make the header fixed height (like 62px or something like that).
2. Give it a background color that you like.
3. Style the list inside the header, use flex to display the items horizontally. We don't want the underline on the links and also we don't want the dots on the lists. Read `text-decoration: none;` and `list-style-type: none;`.
4. Add a hovering effect to the items, maybe changing the background a little bit.

Center your page content below the header.

Tips:

1. Add a class to your sections `.section` and make it `width: 80%` and `margin: 0 auto`, this will center the content.

Style your Staff Table

Style your Contact Form

Tips:

1.  Create a class `.form-control` that wraps the label and the input for each input.

        <div class="form-control">
            <label></label>
            <input></input>
        </div>

Use this class to give the form elements separation with each other and also to set a fixed width for each one. 2. Don't forget to style your button.

Style your footer

## Boolean Algebra

## Programming 101

## JS

## Front End Frameworks

## Final Project
