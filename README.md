# clay-encryption

[JWT(JSON Web Token)](http://self-issued.info/docs/draft-jones-json-web-token.html) encode and decode module for node.js.

Piggybacks off of the [jwt-simple](https://github.com/hokaccha/node-jwt-simple) 

## Install

    $ npm install node-encryption

## Usage

    var Clay = require('jwt-simple');
    
    // Your clay.io secret key
    var secretKey = 'SECRET_KEY';
    
    // The player's unique identifier (received from client js - Clay.player.identifier)
    var userIdentifier = 'SOME_ID';

	// Create object and store user identifier/secret key
	clay = new Clay( userIdentifier, userIdentifier );

    // Example options for an achievment
    var options = { id: 3 };
	
    // encode
    var token = Clay.encode( options );
    
	// Send token as part of options, so client-side: 
	// achievement = new Clay.achievement( { jwt: tokenFromServer } );
	// achievement.award();
