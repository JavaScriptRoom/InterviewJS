# NodeJS Interview Questions: Jordan		

1. What are the benefits and or drawbacks of using the express framework with NodeJS?
2. Explain the development/production package dependencies used by the Node Package Manager (NPM) install command.
    - --save vs --save-dev in package.json
3. How does NodeJS handle child processes?
    - Doesn't have to, it's single threaded (there are advanced ways to use more processes though)
4. What is the core/community established convention for a Node callbacks first parameter?
    - Typically the error object
5. What engine does NodeJS run on?
    - Googles V8 Engine
6. Using only the http module, create a server that listens on any port of your choosing that responds with "Hello, World!"

    ```require('http').createServer();
    var http = require("http").listen(PORT, () => {
        console.log(`Hello world from port ${PORT}!`);
    });```
