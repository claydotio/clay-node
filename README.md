# clay-encryption

[JWT(JSON Web Token)](http://self-issued.info/docs/draft-jones-json-web-token.html) encode and decode module for node.js.

Piggybacks off of the [jwt-simple](https://github.com/hokaccha/node-jwt-simple) 

## Install

    $ npm install clay-encryption

## Usage

    var Clay = require('clay-encryption');
    
    // Your clay.io secret key
    var secretKey = 'SECRET_KEY';
    
    // The player's unique identifier (received from client js - Clay.player.identifier)
    var userIdentifier = 'SOME_ID';

	// Create object and store user identifier/secret key
	var clay = new Clay( userIdentifier, secretKey );

    // Example options for an achievment
    var options = { id: 3 };
	
    // encode
    var token = clay.encode( options );
    
	// Send token as part of options, so client-side: 
	// achievement = new Clay.achievement( { jwt: tokenFromServer } );
	// achievement.award();
