# handlebars-group-every
Helpers for handlebars and express to conditionally render open and closing tags in order to group list items

## Installation
------------
```bash
npm install handlebars-group-every
```

## Usage
-----
### With [Express Handlebars](https://github.com/ericf/express-handlebars)
```javascript
const groupEvery = require('handlebars-group-every');

hbs.handlebars.registerHelper('ifGroupEveryOpen', groupEvery.ifGroupEveryOpen);
hbs.handlebars.registerHelper('ifGroupEveryClose', groupEvery.ifGroupEveryClose);
```

```handlebars
<!-- will wrap every 3 items in <div class="row"> </div> -->
{{#each listItems}}
	{{#ifGroupEveryOpen @index 3}}
	<div class="row">
	{{/ifGroupEveryOpen}}
	
		<div class="col-md-4">{{this}}</div>

	{{#ifGroupEveryClose @index 3}}
	</div>
	{{/ifGroupEveryClose}}
{{/each}}
```