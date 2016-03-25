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
* 
