# Lab 15 Notes


### 1. Zip File for Lab

The lab zip folder includes a `node_modules` folder and `package-lock.json` file. These are not required for your lab attempt, as we will generate these automatically in the lab.

❗️ Don't forget to run `npm init` in your lab folder in codio before working on the lab.

### 2. Mongo Connection Error

If when trying to run MongoDB commands, you get a connection error, your Mongo database probably just isn't running yet! To start your database, run the following command:
```
sudo systemctl start mongod
```
And you can verify it's working by running the `mongosh` command.

*Note: Sometimes this doesn't work on the first try! If connection is still refused after running the above command, try running it once more.*

### 3. Welcoming User

When attempting this task, think carefully about the process from logging in to loading the index page.
<details>
<summary> Hint 1</summary>

The *username* is only shared once (at login), but a *logged in* user may access the homepage many times... How can this information be preserved between pages?
</details>

<details>
<summary> Hint 2 </summary>

Read the `/dologin` code in `server.js`, this is very helpful (it may be easier to read if you expand the `if` statements with newlines after every semi-colon!). Can you see how data persistence is achieved for logging in?

</details>

<details>
<summary> Hint 3 </summary>

```JavaScript
if(result.login.password == pword){
      req.session.loggedin = true; 
      res.redirect('/') 
    }
```
Reviewing the `/dologin` code (above snippet), we can see that the username is grabbed from the post request `req.body.username`, then used for querying the MongoDB. However, this variable is only available within this post request, as the user sent this in the login form.  
  
Upon authentication, the `req.session.loggedin` value is set to `true`, allowing future pages to know the user is logged in and can render the appropriate pages.
</details>






-----------------

### Fun Extra: Styling with Bootstrap
In recent weeks, we have included the Bootstrap framework for making our websites look a little more pretty 💅✨ This framework is very powerful, allowing for lots of customisation by adding predefined classes to HTML elements. 

Bootstrap has a visual [cheatsheet](https://getbootstrap.com/docs/5.0/examples/cheatsheet/) with links to the documentation if you would like to experiment! 

*Note: The CDN we use to load Bootstrap is for version 3, which contains some different class names. If certain classes aren't working, you can update the CDN version by grabbing the css link [here](https://www.bootstrapcdn.com/) and replacing the existing link in `head.ejs`. You can include additional functionality, such as JS animations, by also importing the JavaScript CDN link. Happy experimenting!*
