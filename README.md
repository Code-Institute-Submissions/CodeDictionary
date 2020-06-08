# A Code Dictionary

A Code Dicitonary is a crowd sourced dictionary based off the idea of Urban Dictionary. The aim is to
provide a domain where you can find coding terms for different languages in one place. Generally when I 
need to look up the use of a code term/tag I would have to search across different websites to be
able to find each one, the benefit of my website is that it has different categories of code. You can
currently pick between HTML, CSS, JavaScript and Python code.

Overtime the users of the website would build the database of definitions, and eventually have a lot of
coding terms on the website. It would be a great source of information when you just need to quickly
look up how to use a particular term. The terms that are submitted are reviewed before they are allowed
to appear on the website which will help to control whether information submitted is false or not.


## User Experience

The website is for anybody that is learning or using code and needs a location for quick look ups of
terms. The website provides different functions so that the users can either just view already submitted
terms or add terms to the website themselves.

* The website should be responsive to user actions.
* As a user I would like a navigation bar so that I can easily reach different pages of the webiste.
* As a user I would like the links and forms to respond to my click.
* As a user I would like to be able to easily view terms already submitted to the website by other users.
* As a user I would like to add terms to the website myself.
* As a user I would like the option to register and log in to an account I had already created to be able to add terms.
* As a user I would like feedback when I fill a form incorrectly.
* As a user I would like visual indication on which buttons/links I am about to press.


## Existing Features

### Navigation:
There is a navigation bar on the desktop version and a navigation menu which expands when clicked on
mobile devices. This provides the user with links to all of the available pages to them. When clicked
the user will be taken to the corresponding page.

### To view existing terms:
This is easily done as on the home page there is a category provided for each coding language in the 
database which can be clicked on. When clicked it will take you to a page of all the terms submitted 
into that category. These terms are displayed in cards which are neatly arranged to easily display the
information of each term. All users, regardless if they have an account or not, will be able to see
the already submitted terms. There is a card generated by a for loop for each of the terms in the database.

### Registering an account:
You have the option to sign up to the website. This is provided by a form which you access through the
sign up button either in the navigation bar on desktop, the navigation menu on mobile, or the footer. 
Once you have filled out all of the form inputs then you can click the button to register your account.
The account will then be inputted into the database.
You will be logged in to the account as soon as you register and be returned to the home page. 

### Log in to an already created account:
If you have just registered your account then you will be already logged in. If you are re-visiting the 
website then you have the option to log in through the navigation bar on desktop or the navigation menu
on mobile. This will take the user to a form in which they have to fill with the information of their 
account. Once this is completed and submitted then the user will be logged in if the account information
is correct. Once logged in you will be returned to the home page.

### Visual indication if you are logged in or not:
Once logged in to your account, you will see in the navigation bar on desktop and the navigation menu
on mobile there will be a label which shows you which user you are logged in as. This will display the
username of your account.

### The option to add a term:
If you are logged in, an option will appear in the desktop navigation bar/mobile navigation menu which
is a link to the page with the form which will allow you to add a term. Once all of the options on the
form are filled in then you can submit the term which will then be reviewed before it appears on the
website. Once approved, the term will be entered into the mongo database.
If you are not logged in, when the add term link is clicked, you will be taken to a login form.
Once this form is completed, if the information is correct, you will be taken to the page to add a term.

### The option to log out:
When logged in, an option to log out in the desktop navigation bar/mobile navigation menu will be 
displayed. When clicked, this will delete the session cookie that the user has which means they are
logged out. They will not be able to access the areas of the website that require them to be logged in
until they log back in, such as the add term page. They will be returned to the home page when loggout
out.

### To be notified when a form is not correctly filled in:
All user inputs in each form are required. The form will not be submitted unless they are filled.
When not filled in and the submit button is pressed, a card will appear which will notify the empty field.
Also, some of the forms such as the login forms and register forms require some information to be correct.
In the register form, the username field must contain a username that is not already in the database. The user
will be notified by a flash card by flask if the username is already in use. The passwords in the register
form must also match, the user will be notified in the same way if this requirement is not met.
In the login forms if the username or password does not match that of one in the database, the user will
be notifed by a flash card by flask that the username/password combination is incorrect. It does not inform 
the user which is incorrect as to add more security to accounts.

### Responsive navigation bar:
The navigation bar/menu for mobile changes depending on whether you are logged in or not, and also if you are an admin. 
This is done by using if statements in the html.
If you are not logged in you will have the options of:
* "Home", which links to the home page.
* "Add Term", which will take you to a login page and then to the add term page once logged in.
* "Login", which will take you to a login page and then to the home page once logged in.
* "Sign Up", which will take you to the sign up page, and then to the home page once you complete it.

If you are logged in as a user you have the options of:
* "Home", which links to the home page.
* "Add Term", which will take you straight to the add term page.
* "Logout", which will delete your session and take you to the home page.

If you are logged in as an admin you have the options of:
* "Home", which links to the home page.
* "Add Term", which will take you straight to the add term page.
* "Logout", which will delete your session and take you to the home page.
* "Admin", which takes you to a page where you can approve/disapprove submitted terms.

### Mobile device styles:
The desktop and mobile devices have different layouts.
Term card layouts for desktop will have two cards side by side so that the card does not stretch the whole width of the screen.
For mobile each card will have a row on its own, so that it is not too small when next to another. The cards will appear one above
another.
For the navigation on desktop the links will appear on the right side of the nav bar so that they are easily seen.
For the navigation on mobile, the links are hidden behind a menu button which brings out a side panel with the links that overlays the
website when clicked. This is so that the links are not squashed onto the nav bar.


## Features to implement in the future:

### A contact form:
Currently the only way to contact me if there are any issues is by using the email address provided in the footer. I would like to
use an API which will be linked to a contact page with a form in it. This form will be available for users to fill out and then 
once submitted it will send an email to my account. The user will then receive visual indication on whether the email has been sent.

### The option to edit a term they created:
Once the user submits their term, they do not have the option to delete it or edit it from the website. Only the admin has this 
functionality. I would like to add a function which links each term ID to the user that created that term. The user would then
have the option to edit the term through a form, which then uses the update method to update that term, or to have the option to
completely delete that term from the database. This will help if they inputted the wrong information or if they want to change some
of the information.

### A search bar:
If the database was to get lots of terms added to it, it could be a chore to search for each of the terms you want to find. A search
bar would search for the title of each card and then only show the corresponding cards. This would make term lookup a look quicker
as you wouldn't have to scroll throught the page to find the term.

### A duplicate term function:
When a duplicate term would be submitted, for example if two "<body>" terms were to be submitted on the HTML page, if would not just
display both of those cards on the page. It would create a category within the HTML category which then contains these two cards.
When this new category card is clicked on it will show all the cards that have been created for the body tag.


### An upvote system:
There is no system in place to stop duplicate terms to be submitted to the database. Using Urban Dictionary as an idea, I would like
to implement an upvote system which allows users to either upvote or downvote a term. The terms will display in order of votes, with
most voted being at the top of the page. This would then filter out the best results for each term within the search, or the category
for the multiple terms.


## Technologies used:

### Materialize: https://materializecss.com/
I used Materialize as the main framework for my website, it provided the website structure and layout. Also, it was used
it was used to help the styling of the forms, cards, nav bar and footer.

### Material Icons: https://material.io/resources/icons/?style=baseline
I use Material Icons for the icons on the register form and the form to add a term, also for the mobile nav bar menu icon.

### Google Fonts: https://fonts.google.com/ 
This was used for the font of the text and titles.

### jQuery: jQuery: https://jquery.com/
To help with manipulation of the DOM and Materialize requiered jQuery for some of the html elements to work.

### Google Developer Tools: 
This was used to test the website and find bugs.

### W3Schools: https://www.w3schools.com/cssref/css_colors.asp
This helped to choose the colors for my css.

### Flask: https://flask.palletsprojects.com/en/1.1.x/quickstart/
Flask helps with the rendering of each page, creating the login sessions, the interaction with the mongo database and the flash
cards for the user interaction.

### Bcrypt
I used Bcrypt to hash the passwords of users when they register. This is so that the password in the database is hashed rather
than displaying their password to anyone with access to the database.

### PyMongo:
I use pymongo to create for loops and if statements in the html, which then generates the cards for the categories
and for each of the term within the database. I also use if statements within the nav bar/nav menu to customize it depending
on if you are logged in or not.

### Bson:
This was used to help put the ID of terms into a format that mongodb could read.

### MongoDB: https://www.mongodb.com/
This is the website i use to store my databse. 


## References:

### Help building the login/register system and forms:
https://www.youtube.com/watch?v=vVx1737auSE
https://github.com/PrettyPrinted/mongodb-user-login

### The flash cards:
https://flask.palletsprojects.com/en/1.1.x/patterns/flashing/

### Help with session issue:
https://developer.ibm.com/qradar/2018/10/03/secret-key-session-python-apps/


## Testing:

### Navigation Bar Sizing:
1. Change the screen size, when below 992px width it should change from the desktop view to the mobile view.

### Admin Login:
1. If logged in, verify that you have the option to add terms, logout and to visit the admin page.
2. If logged in, verify that the sign up and login links disappear.

### User Login:
1. If logged in, verify that you have the option to add terms and logout.
2. If logged in, verify that the sign up and login links disappear.

### Navigation Bar Desktop:
1. Click the "home" link, it should take you to the home page.
2. Click the "add term" link, if logged in it should take you to the add term page, if not logged in it should take you to a login page, and then to the add term page once logged in.
3. click the "login" link, it should take you to the login page.
4. click the "logout" link (if logged in), it should log you out and take you to the home page.
5. click the "admin" link (if admin), it should take you to the admin page.
6. click the "sign up" link, it should take you to the sign up page.
7. Once logged in, the nav bar should display "User: (Username)".
8. Click the "Code Dictionary" title, it should link to the home page.

### Navigation Mobile Menu:
1. Click the menu icon, it should bring out the overlay with links. 
1. Click the "home" link, it should take you to the home page.
2. Click the "add term" link, if logged in it should take you to the add term page, if not logged in it should take you to a login page.
3. click the "login" link, it should take you to the login page.
4. click the "logout" link (if logged in), it should log you out and take you to the home page.
5. click the "admin" link (if admin), it should take you to the admin page.
6. click the "sign up" link, it should take you to the sign up page.
7. Once logged in, the nav bar should display "User: (Username)".
8. Click the "Code Dictionary" title, it should link to the home page.

### Footer:
1. Click the "sign up" text, it should take you to the sign up page.

### Home Page:
1. Hover over each of the cards, they should slightly change colour and the cursor turn to a pointer.
2. Click each card and verify it takes you to a page with cards of the corresponding category.

### Category Page (after clicking home page category):
1. Verfiy that the terms all belong to the category that was clicked on the home page.
2. The cards should have a term title, category, definition, and example.
3. Change the screen width to below 1200px and the cards should change from 2 columns to 1 which fits the screen.
4. Verify that all terms have the key value pair of {"approved": "yes"} in the mongodb.

### Add Term Page:
1. Try submitting the form without a category selected, it should not submit.
2. Try submitting without a term name, it should notify that it needs to be filled in.
3. Try submitting without a term description, it should notify that it needs to be filled in.
4. Try submitting without a example of use, it should notify that it needs to be filled in.
5. Submit a complete form and verify it takes you to the home page.
6. Change the screen size to below 600px width and verify the form changes from 2 columns to 1 which fits the screen.

### Main Login Page (Login nav bar link):
1. Try submitting without username, it should notify that it needs to be filled.
2. Try submitting without password, it should notify that it needs to be filled.
3. Use and incorrect username or password, it should notify that the combination doesnt match.
4. Submit with the correct information, it should take you to the home page and create your session.

### Add Term Login Page (Add Term nav bar link if not logged in):
1. Try submitting without username, it should notify that it needs to be filled.
2. Try submitting without password, it should notify that it needs to be filled.
3. Use and incorrect username or password, it should notify that the combination doesnt match.
4. Submit with the correct information, it should take you to the add term and create your session.

### Sign Up Page:
1. Try submitting without username, it should notify that it needs to be filled.
2. Try submitting without email, it should notify that it needs to be filled.
3. Try submitting without password, it should notify that it needs to be filled.
4. Try submitting without repeat password, it should notify that it needs to be filled.
5. Try submitting with a username already in use, it should notify that the username already exists.
6. Try submitted with an invalid email format, it should notify that it is invalid.
7. Try submitting when the 2 password fields are different, it should notify that they do not match.
8. Submit with the correct information, it should create a sesson and log you in, it should also take you to the home page and input the user to mongodb.
9. Veryify that the user has the key value pair of {"admin": "no"} in mongodb.

### Admin Page:
1. Verify that the terms displayed have the key value pair of {"approved": "no"} in mongodb.
2. Click the delete button, it should delete the term from the mongodb.
3. Click the approve button, it should update the key value pair of {"approved": "no"} to {"approved": "yes"}in mongodb.
4. Verify that when deleted or approved the term no long appears on the admin page.
5. Change the screen width to below 1200px and the cards should change from 2 columns to 1 which fits the screen.

### Select Dropdown on Add Term Page:
1. Click the select box and verify that it contains all of the categories present in the mongodb.

### Bugs I Encounted:
1. When in the mobile device view, the html page would not fill the entire screen. This was caused by an overflow of the footer, this was solved by adding break-word in the css to the footer text.
2. The select dropdown would not display the categories if you wanted to add a 2nd term, this was fixed by changing my route to a redirect instead of render_template so it wouldnt render the template a second time if you wanted to add a second term.
3. I got an error when using the for loops to generate the term cards, this was an issue where I was referencing the wrong values after I had set them in the for loop.

All of the issues I encounted were fixed with the help from people on Slack and my tutor.

## Directory Structure and File Naming:
All of the HTML pages are within a folder named "templates" and are name according to their function. The CSS file was put into
folders called "static" and then "css" folder. This is because Flask requires them to be organised like this. All other files are kept out
of these two folders.

## Version Control:
I used Github to control versions of the code. I would push the code to the repository every time I made a significant change or fixed a bug.
This allowed me to have back ups of earlier code just incase I deleted a file in the local repository or made an error in new code I was writing.
I could go back to earlier versions if needed.

## Difference in deployed version and development version:
In the development version, DEBUG is set to true so that I could easily find errors in my code while developing. When I deployed the project I 
turned DEBUG off so that no information is leaked such as env files.
The env variable is not pushed to Github as it would compromise the security of my database account, instead it is stored as a variable on Heroku.

## Deployment Process (GitHub):

First, create a repository in GitHub, then launch Gitpod through GitHub. 
This will make sure that the remote origin for the push to GitHub is already added – 
allowing you to push your files to your repository without having to add the remote origin manually. 
When the project is first stated you need to create a local repository, this is where changes that are made locally are saved to. 
From this you push them to the repository was created earlier, this is where all the versions that have been uploaded in the past 
and where the final webpage is saved. You can then access the code for each time you have pushed to this repository. To do this 
you have to use commands in the terminal of Gitpod.

1. Git init (to create the local repository).
2. Git status (to check which files are not tracked/have been changed or removed).
3. Git add “example.html” (to add the file to the repository).
4. Git commit -m “version name” (to save your changes to the local repository).
5. Git push (to upload the local repository to the remote repository on GitHub).

To run my code locally you can visit the website "https://github.com/LaDawson/myCodeDictionary" which takes you to the repository 
for my project. Here you will be able to see the latest version I have uploaded. The most recent version will be the first few files 
you can see, you can open these to see my code. There is also an option to download or clone my code. You can clone the repository
to GitHub Desktop by clicking the "Open in Desktop" button after clicking the "Clone or Download" button.

If you copy the link provided when you click the clone/download button, then follow these steps to run it locally:

Open Git Bash
Change the current working directory to the location where you want the cloned directory to be made.
Type git clone, and then paste the URL you copied.
Press enter and your local clone will be created.

## Deployment Process (Heroku):
To deploy to heroku you need the following files:
* requirements.txt - get this by typing "pip3 freeze --local > requirements.txt" into the terminal.
* Procfile - just add this in the root of your project folder. Enter the values "web: python app.py" with the correct python file name.
This is so that heroku can install the needed things to run your app and so that it recognises it as a python app.

1. Create an app on Heroku
2. Type "heroku login" into the terminal
3. Enter your account details
4. Type "git init" into the terminal
5. Type "git remote add heroku "your Heroku git URL" into the terminal
6. Type "git add ." into the terminal
7. Type "git commint -m "Version Name"" into the terminal
8. Type "git push -u heroku master" into the terminal
9. Set your PORT and IP variables on heroku which you refer to in the python file
