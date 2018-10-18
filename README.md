# node-js-heroku-test

this project exists because heroku needs a root level to work with and I couldn't have all the other projects up if I didn't want them to go up.  This is originally based on https://github.com/martingardner/nodejs-learning-projects

#node inherant variables
* __dirname is inherant in node as part of the main() wrapper function it calculates base to point that __dirname is called.


#nodemon
* nodemon {{file to start}} instead of node {{file to start}}
* nodemon doesn't inherantly watch for certain extension changes like hbs, but in the nodemon command
  nodemon {{file to start}} -e {{file extensions separated by commas}} ((Looks like there is a bug for windows that hbs won't trigger restart for this))

#hbs (handlebars)
* similar to laravel blade {{ varname }} for injection
* for partials {{> partialname}}
* hbs inherently looks for a views folder with partials looked for within that.
* can register partial for data used frequently 
	* for example: hbs.registerHelper('getCurrentYear', ()=> {
	return new Date().getFullYear();
})  and then call it in a hbs file the same as you would any other variable {{getCurrentYear}}
* can also register partials to act as formatters
	* for example: hbs.registerHelper('screamIt', (text)=> {
	return text.toUpperCase();
});  and then call it in a hbs file {{screamIt stringVariable}} -- note it's not called like a normal method, there is a space between what is being passed in and not ().

#heroku
* [cli] heroku create - creates a heroku app.
* [cli] git push heroku - pushes project to remote heroku project (note on new project this won't be attached)
* [cli] $ heroku git:remote -a appname - ties the local git project to a remote heroku project
* [cli] heroku open - will open the project in a default browser

#node-web-server (class)
* npm install
* uses express npm package
* hbs view engine (wrapper for handlebars for express to make dynamic views)
* for Heroku release, changing port to be dynamic or 3000 depending on local environment or whatever Heroku gives
* also need to give start script in package.json with "node server.js" in it.  Heroku looks at start script in order to run it.