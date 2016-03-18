# MVC, 3/9/16

## What does it mean?

* "MVC": modal, view controller
  * a proposal for how to organize code in a user-facing application
  * has had multiple interpretations, historically
  * sorts into 3 separate types of object/class components
    * Model: manages program state
    * View: presents state to user
    * Controller: Receives input from user

![picture alt](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/2000px-MVC-Process.svg.png)

* "MVC framework"
  * a library that helps you write code in the MVC style of architecture
  * can do some things automatically since it knows you'll be writing in that style
  * backbone, ember, angular

## How does MVC help you?

* using the 3 components allows for a separation of concerns
  * limits on interactions between modules of different components
  * limits on interactions between modules within a component
* Breaking each component into many modules allows reasoning in isolation
  * static analysis limits on code
    * example: code for different view modules lives in different files, without references to each other
  * runtime limits on objects
    * example: different view objects will have limited access to other view objects

## A model instance should also...

* have relationships to other model instances (perhaps represented as properties)
* intervene on property access, to facilitate binding
  * where is the data actually stored
* provide an eventing interface
  * the way that MVC works, the view needs to know when the modal has *changed*
  * this framework should provide that

## A Model Instance Should Never

* have knowledge of any more other models than necessary
* have knowledge of any views (or DOM nodes) whatsoever

## Why would I want a View instance?
* It will map from one modal instance to one on-screen rectangle
* a map from abstract truth to UX

## A view instance should also

* correspond with a single DOM node
  * (Not all DOM nodes have associated view instances)
* compose itself out of subviews (optional)
  * and possibly keep references to them
* listen for model events
  * Transform to any relevant screen update commands
  * Avoids model instances depending on view instances
* set up a controller for user input int hat area
  * (or, optionally, act as a controller itself)

## A view instance should never

* Have knowledge of any sibling views
  * So never run a full search of the DOM
* have knowledge of its own parent
* have knowledge of any modals other than the one it is projecting

## Why would I want a controller instance?

* (look at the slides)

## Graph/Tree Disparity

* View instances form a Tree
  * Consider the nature of the DOM
* Model instances form a graph
  * Your data may have arbitrary relationships
* Trees and graphs have big differences
  * You you really can't mix view code and model code
  * A model object: data for 0,1 or many view objects
  * a view object: associated with 0 or 1 model objects

# Secrets of Backbone

* The Town Hall

## Lifecycle of a Song

* We start in the index
* App Modal
  * has property current song
  * when that changes
    * execute this function
