# NodeJS Interview Questions: Jordan		

NodeJS Section

Easy
1. What engine does NodeJS run on?
-Googles V8 Engine
2. What is the typical first parameter in a NodeJS callback function for core modules? 
-Typically the error object is the first parameter of a callback function

Medium
3. How do you handle an unhandled exception in NodeJS? Use the process object to create an exception handler for these.

Answer:
    process.on('uncaughtException', (err) => {
        console.log('Caught exception: ' + err);
    });

What is "callback hell"? Describe a solution methodology or modules that help resolve this issue.
Answer:
Promises are a good methodology to solve callback hell (nested callbacks), often caused by NodeJS’s asynchronous event loop. A good library for promise handling is Bluebird, but native Promises are also an option, using the resolve, reject pattern.

The async module provides a good waterfall style pattern to asynchronous methods, in an array of cascading methods. This is useful for multiple async calls, such as multiple mongodb queries that depend on each other’s results.

Explain the importance of package.json and NPM for a NodeJS project.
Answer
NPM looks for a package.json file in the structure, and when you run npm install on a project, it will find your dependencies, which are created when you install a module upon creation via npm install module --save (--sav dev is an option for development environment dependencies)

Hard:
6. NodeJS utilizes the express framework to handle HTTP routing and other API style services. Assuming express, and bodyParse are already included, and the server is listening on port 8080, write code to expose a directory named ”public” for static material like html, css, and javascript files. Assume the express variable is named “app”. On the route (GET method) /foo, render the HTML file “foo.html”. On the route (POST method) /bar, send a small object (can be anything, content is irrelevant) response.

Answer:

    app.use("/", express.static(__dirname+"/public")); //expose public dir
    app.get(“/foo”, function(req, res) {
        res.render(“foo.html”);
    });
    app.post(“/bar”, function(req, res) {
        res.send({flag:true});
    });
