##node-api-message

Please Share on Twitter if you like #NodeAPIMessage

<a href="https://twitter.com/intent/tweet?hashtags=NodeAPIMessage&amp;&amp;text=Check%20out%20this%20repo%20on%20github&amp;tw_p=tweetbutton&amp;url=https%3A%2F%2Fgithub.com%2Fdropshape&amp;via=dropshape" style="float:right">
<img src="https://raw.github.com/dropshape/NodeAPIMessage/master/twittershare.png">
</a>

##Description
Node-API-Message is an ExpressJS extension that allows you to create API messages that are consistent across  your application. These messages are stored in a MongoDB using Mongoose so that you can track all API messages within your application.

##Installation
    npm install node-api-message --save

##Usage

####Initialization
After initializing node-api-message you will have a new method available on your express response objects.

    var mongoose  = require('mongoose').createConnection('mongodb://localhost:3001/TestingDB');
    var apiMessage = require('node-api-message').initialize(mongoose);
    //Tell express to use apiMessage
    express.use(apiMessage);

####apiMessage

    var Status = require('node-api-message').Status;
    app.get('/something', function(req, res){
        res.apiMessage(Status.OK, 'some message here', { data: 'data'});
    });
    
**Status**: A valid HTTP Status code.

**Message**: A message to be returned with the response object. This Message is used as the key for uniqueness in MongoDB.

**Data**: Optional data to be sent with the response. This data is not saved in MongoDB.

The output from the above message would look like this.

    {
        data: { data: 'data' },
        code: 2000000,
        status: 200,
        message: 'some message here',
        href: '/apimessages/2000000',
        type: 'apimessage'
    }

##Contributing
1. Fork the git repository
1. Add some awesome code
1. Add some awesome tests
1. Run the tests and jshint using the grunt command
1. Create a Pull Request

##ChangeList
####0.0.2
Added Documentation to README.md file
####0.0.1 
Initial Commit




Please Share on Twitter if you like #NodeAPIMessage

<a href="https://twitter.com/intent/tweet?hashtags=NodeAPIMessage&amp;&amp;text=Check%20out%20this%20repo%20on%20github&amp;tw_p=tweetbutton&amp;url=https%3A%2F%2Fgithub.com%2Fdropshape&amp;via=dropshape" style="float:right">
<img src="https://raw.github.com/dropshape/NodeAPIMessage/master/twittershare.png">
</a>