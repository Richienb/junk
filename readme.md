# junk

> Filter out [system junk files](test.js) like `.DS_Store` and `Thumbs.db`


## Install

```
$ npm install junk
```


## Usage

```js
const {promises: fs} = require('fs');
const junk = require('junk');

(async () => {
	const files = await fs.readdir('some/path');

	console.log(files);
	//=> ['.DS_Store', 'test.jpg']

	console.log(files.filter(junk.not));
	//=> ['test.jpg']
})();
```


## API

### junk.is(filename)

Returns `true` if `filename` matches a junk file.

### junk.not(filename)

Returns `true` if `filename` doesn't match a junk file.

### junk.regex

Regex used for matching junk files.


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
