# Gulp CSS Snippets

Gulp module for CSS snippets require from remote server.


## Usage
In your `gulpfile.js`:
```
gulp.src('./css/snippet-require.css')
	.pipe(cssSnippets({
	    fileName: 'snippet-components.css',
	    base: 'https://rawgit.com/2createStudio/postcss-require-lib/master/snippets/'
	}))
	.pipe(gulp.dest('./css'));
```

The require file (`snippet-require.css`) should use this syntax:
```
import('snippetFoo');
import('snippetBar');
```

The structure on the remote server should look like this:

```
mainDir
+-- snippetFoo
|   +-- main.css
|   +-- README.md
+-- snippetBar
|   +-- main.css
|   +-- README.md
```

The content of `snippetFoo/main.css` will be the contactenated content of the snippet `main.css` files.
