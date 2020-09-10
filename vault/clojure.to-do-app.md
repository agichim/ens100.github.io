---
id: 8812f96a-e15c-487a-94fd-b0ba14de4cfd
title: To Do Application
desc: ''
updated: 1599582904292
created: 1599582904292
nav_order: 3.5
---

# Clojure To Do App

Today I took a little bit of time out from reading and followed a video to set up a web app - I wanted to get away from the theory for a second and see something live and tangible of what Clojure can achieve. I followed a Purely Functional video on web app testing and was able to follow this and complete the app.

Although a number of things were advanced, there were plenty of items which made sense from the reading. Sometimes seeing something live just makes things so much easier to understand and follow.

- Introduction:
    - How to determine which server side system to use? There are many out there:
    -  Heroku
    -  Jetty
    -  tomcat
    -  mongrel2
    -  Ring - takes common abstraction to build webapp. Most projects use ring.
- Run a server
    - To add a dependency search for the latest version "Clojure ring GitHub" [site](https://github.com/ens100/Learning-Clojure/blob/master/post/2020-08-10.md)
    -  Library name and version number are what is needed to port over.
    -  copy entire ring package - paste into project file (under dependencies)
    -  Once loaded into the IDE need to add a  require function in the namespace
        - `(:require [ring.adapter.jetty :as jetty])`
    -  Add a port call
        - `(defn -main [port] (jetty/run-jetty (fn [req] {:status 200 :body "Hello, World!" :headers {}}) {:port (Integer. port)}))`
    - Go to PowerShell and the root of the project.clj run `lein run 8000`  and go to `http://localhost:8000/` which should show "Hello World"
    -  to kill 8000 
        - `netstat  -ano  |  findstr  8000`
        - `taskkill  /F  /PID  XXXX`
- Ring - there are three parts:
    -  Adapter - this is like Jetty that we ran
        -  take http request - convert to ring and pass to handler
    -  handler
        -  takes a ring request and outputs a ring response
        -  http request comes in to the adapter - converts and pushes to handler, handler returns response
        -  has three core concepts
            -  status - http status code
            -  body - string, file
            -  headings
    - middleware
        -  Connect between adapter and handler
        -  can have many middlewares = middleware stack
        -  take a function and returns a different handler.
-  wrap-reload - avoids having to continuously kill and restart localhost
    -  every request - reloads change files.
    -  need to wrap handler in a var - value in var gets reloaded.
    -  to get this running need to add a dependency  `[ring.middleware.reload :refer [wrap-reload]`
    -  add a profile for development `(defn  -dev-main [port]  (jetty/run-jetty (wrap-reload #'greet) {:port (Integer. port)}))`
    -  `:profiles {:dev :main todo.core/-dev-main}})`
    -  kill server and re-run
    -  Too add in a page reference add a conditional function and then add in the test. If` (= "/goodbye" (:uri req))` - is the url = goodbye
-  compojure -takes a library of urls and returns.
    -  as adding  new library will need to kill and restart server
    -  find compojure on GitHub and like with ring add it as a dependency
    -  `[compojure.core :refer [defroutes GET]]` and `[compojure.route :refer [not-found]]`
    -  add defroutes to the body
    -  to add more such as /goodbye - just add to the handler as did for hello
- Posting
    -   To post the app online need to have Heroku and Git installed. Once these are installed and set up.
    -   Need to add a couple more items to the project file so that it can read it properly.
    -   Also need to create a new `Procfile` - this is so that Heroku knows what to read.
    -   Sync up git and Heroku

Need to study this latter part in a lot more depth but seem to have managed to get my app up and running. Quite cool.
