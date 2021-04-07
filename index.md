## Digits

<img src="doc/Landing.jpg">

Digits is an application that allows the user to:

  * Register an account
  * Create and manage a set of contacts.
  * Add a set of timestamped notes regarding their interactions with each contact.

## Installation

First, [install Meteor](https://www.meteor.com/install).

Next, go to [https://github.com/adamjparrilla/digits/tree/master](https://github.com/adamjparrilla/digits/tree/master) to download a copy of Digits. Note that Digits is a private repo and so you will need to request permission from the author to gain access to the repo.

Third, go to your newly created repository, and click the "Clone or download" button to download your new GitHub repo to your local file system.  Using [GitHub Desktop](https://desktop.github.com/) is a great choice if you use MacOS or Windows.

Fourth, cd into the app directory and install the required libraries with:

```
$ meteor npm install
```

## Running the system

Once the libraries are installed, you can run the application by invoking:

```
$ meteor npm run start
```

The first time you run the app, it will create some default users and data. Here is the output:

```
meteor npm run start

> meteor-application-template-react@ start C:\Users\adpar\Documents\GitHub\digits\app
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ C:\Users\adpar\Documents\GitHub\digits\app ]]]]]

=> Started proxy.
=> Started MongoDB.
W20210406-21:16:17.777(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20210406-21:16:17.989(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20210406-21:16:17.990(-10)? (STDERR) approximately three times slower than the native implementation.
W20210406-21:16:17.991(-10)? (STDERR) In order to use the native implementation instead, run
W20210406-21:16:17.991(-10)? (STDERR) 
W20210406-21:16:17.992(-10)? (STDERR)   meteor npm install --save bcrypt
W20210406-21:16:17.993(-10)? (STDERR) 
W20210406-21:16:17.993(-10)? (STDERR) in the root directory of your application.
I20210406-21:16:20.743(-10)? Creating the default user(s)
I20210406-21:16:20.744(-10)?   Creating user admin@foo.com.
I20210406-21:16:21.197(-10)?   Creating user john@foo.com.
I20210406-21:16:21.572(-10)? Creating default contact.
I20210406-21:16:21.573(-10)?   Adding: Johnson (john@foo.com)
I20210406-21:16:21.607(-10)?   Adding: Casanova (john@foo.com)
I20210406-21:16:21.619(-10)?   Adding: Binsted (admin@foo.com)
I20210406-21:16:21.802(-10)? Monti APM: completed instrumenting the app
=> Started your app.

=> App running at: http://localhost:3000/
```


### Note regarding "bcrypt warning"

You will also get the following message when you run this application:

```
Note: you are using a pure-JavaScript implementation of bcrypt.
While this implementation will work correctly, it is known to be
approximately three times slower than the native implementation.
In order to use the native implementation instead, run

  meteor npm install --save bcrypt

in the root directory of your application.
```

On some operating systems (particularly Windows), installing bcrypt is much more difficult than implied by the above message. Bcrypt is only used in Meteor for password checking, so the performance implications are negligible until your site has very high traffic. You can safely ignore this warning without any problems during initial stages of development.

If all goes well, the template application will appear at http://localhost:3000. You can login using the credentials in settings.development.json, or else register a new account.

Lastly, you can run ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

### User Interface Walkthrough

Landing Page:
When you first bring up the application, you will see the landing page that provides a brief introduction to the capabilities of Digits:

<img src="doc/Landing.jpg">

Register:
If you do not yet have an account on the system, you can register by clicking on “Login”, then “Sign Up”:

<img src="doc/Landing.jpg">

Sign in:
Click on the Login link, then click on the Signin link to bring up the Sign In page which allows you to login:

<img src="doc/Landing.jpg">

User home page
After successfully logging in, the system takes you to your home page. It is just like the landing page, but the NavBar contains links to list contact and add new contacts:

<img src="doc/Landing.jpg">

List Contacts
Clicking on the List Contacts link brings up a page that lists all of the contacts associated with the logged in user:

<img src="doc/Landing.jpg">

This page also allows the user to add timestamped “notes” detailing interactions they’ve had with the Contact. For example:

<img src="doc/Landing.jpg">

Edit Contacts
From the List Contacts page, the user can click the “Edit” link associated with any Contact to bring up a page that allows that Contact information to be edited:

<img src="doc/Landing.jpg">

Admin mode
It is possible to designate one or more users as “Admins” through the settings file. When a user has the Admin role, they get access to a special NavBar link that retrieves a page listing all Contacts associated with all users:

<img src="doc/Landing.jpg">
