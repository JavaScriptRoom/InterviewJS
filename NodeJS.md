# NodeJS Interview Questions: Jordan		

    require('http').createServer( (req, res) => {
        // make me serve different files on /foo vs /bar
    });

What is "callback hell" and describe a solution methodology.

How do you handle an unhandled exception in NodeJS? Use the process object to create an exception handler for these.

    process.on('uncaughtException', function(err) {
        console.log('Caught exception: ' + err);
    });
