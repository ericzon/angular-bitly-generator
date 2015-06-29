# angular-bitly-generator

Lib created to generate bitly links on-the-fly. Two flavours: service and directive.
Fallback: if it exceeds the rate limit, returns the original link. It has been tested with angular 1.2.x & 1.4.

@See http://dev.bitly.com/rate_limiting.html

## Installation:

	bower install angular-bitly-generator

	And then add the script to your main html file:

	<script type="text/javascript" src="bitly-generator.js"></script>

## Configuration:

	.config(['bitlyProvider', function (bitlyProvider) {
		bitlyProvider.cfgBitly({
			login: 'myuser',
			api: 'myapikey',
			domain: 'https://api-ssl.bitly.com', 	// optional. (http://api.bit.ly by default)
			version: '3' 							// optional. Tested with bitly api versions: 2.0.1 & 3 (3 by default)
		});
	}])

## Usage

**Example 1:**

	<a href="http://www.ondho.com" bitly-generator>Ondho</a> automagically it turns into: <a href="http://bit.ly/ondho">Ondho</a>

**Example 2:**

	bitly.getShortUrl(longUrl).then(function(data){
		console.log("bit.ly DATA:", data);
		$scope.bitlyUrl = data;
		console.log("Bit.ly", $scope.bitlyUrl);
	}, function(e){
		console.log("Bit.ly ERROR: ", e);
		$scope.bitlyUrl = e;
	});


## Dependencies

  None :)

## Tests

  Not yet :(

## Contributing

In lieu of a formal styleguide, take care to maintain the existing coding style.
Add unit tests for any new or changed functionality. Lint and test your code.

## Author

[Eric Lara](https://www.twitter.com/EricLaraAmat), at [Ondho](http://www.ondho.com).

## License

  MIT

## Changelog

* 0.0.3 Trivial update.

  0.0.2 Added better documentation.

  0.0.1 Initial commit
