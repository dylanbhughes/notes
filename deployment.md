# Deployment

* LAST ONE BEFORE PROJECT PORTION

## Demystifying Deployment

* What does it mean to be 'deployed'?
  * Your app running on a remote computer
    * (the code sits somewhere else that is "always up")
* But how do we do it?
  * prepare your app for a prod env
    * it's different for every env
  * Get the code on the machine
    * it's different for every environment
  * Start your app
    * It's different for every environment
  * Cross your fingers
    * Because magic, amiright?
* Common Pitfalls
  * Hardcoded assumptions
  * Failure to design a debuggable app
  * Lack of deployment automation
    * Literally one command
  * Inability to scale by (unconscious) design
* Hardcoded Assumptions
  * no hardcoded links in your html, js, required modules that aren't saved
  * listening at specific ports
* How to avoid hardcoded assumptions
  * Use environment variables to determine the port
    * ```app.listen(process.env.PORT)```
  * Use root-relative URLs instead of absolute URLs
    * ```<a href='/signin'> Sign in</a>```
  * Install npm modules with --save
    * --save-dev means that it's a dev only dependency
* Failure to design a debuggable app
  * have error handling
  * don't ignore db connection errors
  * LOG YOUR GODDAMN ERRORS
* How to be debuggable
  * Handle errors and log them
  ```js
  if (err) {
    console.error('The whozit broke when poked');
    return next(err);
  }
  ```
* Lack of Automation
  * Your deployment process should *not* go like this:
    1. 2 man team manually builds project using punchcards
    2. Code smuggled across state lines in unassuming Volvo
    3. Code loaded onto server using shovel
    4. Server started by hand crank
    5. Server poked in production environment to see if it works
    6. Server kicked if it misbehaves
* How to Automate?
  * Take advantage of deployment scripts*
    * need to install bower components
    * need to run a grunt task?
    * need to touch a log file?
  * Publish from source control
    * Deployment is as simple as pushing a branch (Azure, Heroku)
  * Setup deployment scripts
  * Start your app using the right method
    * Procfile on Heroku
    * 'npm start' script on Azure

## The Sprint Intro

* Gonna have to do some stuff
  * Gruntfile
    * There's some stuff you're gonna have to change.
    * Concat your js files -> uglify this
    * css min
    * shell
      * prodserver
      * you need to research about what this thing does
    * make sure ```grunt.loadnpmtasks()``` lines are working correctly
    * also need to explicitly register grunt tasks
    * css min and uglify destination files are dist
