# OWASP Enterprise Security API (ESAPI)

[![Build Status](https://travis-ci.org/ESAPI/owasp-esapi-js.svg?branch=master)](https://travis-ci.org/ESAPI/owasp-esapi-js)

This file is part of the Open Web Application Security Project (OWASP)
Enterprise Security API (ESAPI) project. For details, please see
http://www.owasp.org/index.php/ESAPI.

Copyright (c) 2008 - The OWASP Foundation

The ESAPI is published by OWASP under the BSD license. You should read and accept the
LICENSE before you use, modify, and/or redistribute this software.

ESAPI

## Installation

```
$ npm install --save-dev ESAPI-JS
```

Installation:
1. Download the distribution zip from http://owasp-esapi-js.googlecode.com
2. Unzip the distribution zip
3. Create a directory on your server, under the web root called esapi4js
4. Copy either esapi.js or esapi-compressed.js from dist/ to your esapi4js directory
5. Create a lib directory under the esapi4js called lib and copy the contents of dist/lib to that directory
6. Create a resources directory under the esapi4js called resources and copy the contents of dist/resources to that directory

## Quick Start:

	<!-- esapi4js dependencies --><script type="text/javascript" language="JavaScript" src="{your_installation_path}/esapi4js/lib/log4js.js"></script>
	<!-- esapi4js i18n resources -->
	<script type="text/javascript" language="JavaScript" src="{your_installation_path}/esapi4js/resources/i18n/ESAPI_Standard_en_US.properties.js"></script>
	<!-- esapi4js configuration -->
	<script type="text/javascript" language="JavaScript" src="{your_installation_path}/esapi4js/resources/Base.esapi.properties.js"></script>
	<!-- esapi4js core -->
	<script type="text/javascript" language="JavaScript" src="{your_installation_path}/esapi4js/esapi.js"></script>

	<script type="text/javascript" language="JavaScript">
	    // Set any custom configuration options here or in an external js file that gets sourced in above.
	    Base.esapi.properties.logging['ApplicationLogger'] = {
	        Level: org.owasp.esapi.Logger.ALL,
    	    Appenders: [ new Log4js.ConsoleAppender() ],
	        LogUrl: true,
	        LogApplicationName: true,
	        EncodingRequired: true
	    };

    Base.esapi.properties.application.Name = "My Application v1.0";

    // Initialize the api
    org.owasp.esapi.ESAPI.initialize();

    // Using the logger
    $ESAPI.logger().getLogger('ApplicationLogger').info(org.owasp.esapi.Logger.EventType.EVENT_SUCCESS, 'This is a test message');

    // Using the encoder
    document.writeln( $ESAPI.encoder().encodeForHTML( "<a href=\"http://owasp-esapi-js.googlecode.com\">Check out esapi4js</a>" ) );

    // Using the validator
    var validateCreditCard = function() {
        return $ESAPI.validator().isValidCreditCard( $('CreditCard').value );
    }
	</script>`


## License

BSD
