critical
========

> Critical Path CSS generation &amp; inlining

## Installation

```
npm install -g critical
```

## Usage

```
var critical = require('critical');
critical({
	  src: 'test/index.html',
	  base: 'test/',
	  styleOutput: 'test/styles.css',
	  width: '480',
	  height: '320',
	  target: 'test/inlined_index.html'
	}, function(output){
		// You now have HTML with inlined critical-path CSS
	});
```

## Why?

### Why is critical-path CSS important?

> CSS is required to construct the render tree for your pages and JavaScript will often block on CSS during initial construction of the page. You should ensure that any non-essential CSS is marked as non-critical (e.g. print and other media queries), and that the amount of critical CSS and the time to deliver it is as small as possible.

### Why should critical-path CSS be inlined?

> For best performance, you may want to consider inlining the critical CSS directly into the HTML document. This eliminates additional roundtrips in the critical path and if done correctly can be used to deliver a “one roundtrip” critical path length where only the HTML is a blocking resource.
