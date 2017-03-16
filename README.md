An easy to use module importer for JS. 

First, run `npm install easy-import --save-dev`.

Next add an entry in to your `.babelrc` file:

```
{
	"plugins": [
		"easy-import"
	]
}
```

Usage:

Simply add a comment as the first line of any file that is used after your app's entry point.

```
//@provides Module
export default class Module { }
```

Anywhere in your app, you can now import this module very simply.

```
import Module from 'Module';
```

Names should be unique to avoid module collision, but namespaces are supported:

```
//@provides Modules/Module
```

```
import Module from 'Modules/Module'
```

The inspiration behind this package is to avoid long and directory specific module finding.

For example, the following line is not uncommon:

```
import Module from '../../../../Module';
```

This is not a new idea, and lots of inpspiration was taken from Facebook's haste/fbjs projects.