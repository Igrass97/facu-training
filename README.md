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
An HTML element is represented with <tag-name>.

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

1. <!DOCTYPE html> instructs the browser that you're using the last version of HTML.
2. <html> the html element wraps all the content of the entire page (root element).
3. <head> acts as a container for all the metadata of the page (stuff that won't appear on the page content but it will affect how it works).
4. <title> the title of the page that will be displayed on the browser.
5. <body> this contains the content that will be visible and rendered by the browser.

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

Hint: with the href attribute of the <a> element, you can also reference another html page.

The columns for the table should be: Employee Name, Role, Seniority (Junior, Semi-senior, Senior) and salary. Include at least 3 employees.
## CSS

## Boolean Algebra

## Programming 101

## JS

## Front End Frameworks

## Final Project
