Node.js project using Express MVC framework to prompt a user to log in via the front end JavaScript Facebook API, and then display the person's Facebook photo, and other details after having been authenticated by Facebook.
=========
Notes from Rich:

I've created a node.js app using the Express MVC framework which allows a user to log into the web page using their Facebook credentials.  I first created the app by using the JavaScript SDK for the web on the Facebook developer site.  I deployed it to Heroku, and added it to a git repository.  I added the Facebook app's App ID and Facebook Secret to the .env file, use npm to update the dependencies listed in the package.json and added the node_modules to the repo as per best practices.

I used node.js installed on my local iMac, along with the Heroku command line toolbelt, git, npm and foreman, along with an app called hammer which uses pow.cx and zip.io to serve up the site for local development web serving and testing.  I used the Sublime Text editor to make changes, foreman to spawn local web processes based on the Procfile.

I adjusted the heroku setup, adding my public keys to the heroku app, pulling the initial Facebook node.js template from where it was installed on Heroku, adjusting the Heroku environment by setting NODE_ENV to production, adding the Facebook App ID and Secret, and setting the remote Heroku master git repository. I adjusted the Heroku dynos to a higher number, and tested the app.

I'm able to use the Facebook client-side Javascript SDK to allow a user to lot in to a web page. 

You may see the deployed app on Heroku.

Note that, I also have created my own Node.js application, installing the Express framework, customizing it and its routes, manually implementing the Javascript SDK per the Facebook Developer docs, but I ended up with a similar result to the Facebook Node.js template.

As another troubleshooting step, I replaced the Facebook JavaScript with the debug version (//connect.facebook.net/en_US/all/debug.js) and set the environment variable to development mode, and monitored log files and the web browser developer console.

Note that my next steps to complete this app will be to send the authorization token that I am already retrieving to Node.js via an AJAX request. I would use jQuery.ajax() asynchronous call to send the authorization token as a key, value pair to Node.js, where I'd then use the Facebook SDK calls to retrieve the user's name and profile image URL to the browser, via values in an ejs file.

