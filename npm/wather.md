## Watch

There are tools that watch files and execute commands when files change, for example watch, onchange, dirwatch, or even nodemon:

```
...
"build": "npm run build:js && npm run build:css && npm run build:html",
 "build:watch": "watch 'npm run build' .",
....
```

## Running multiple tasks

With npm you have two options here - depending on which one is semantically the right fit. You can either use the pre- or post- hooks - which are a good fit if the task is a prerequisite thing (i.e concating js before minfiying it), or you can use the bash && operator - like so:

```
"build": "npm run build:css && npm run build:js",
"prebuild:js": "npm run lint"
```

## Streaming to multiple tasks

One of Gulp’s biggest features is that it streams the output seamlessly from one task to the next (as opposed to Grunt which constantly dips in and out of the filesystem). Bash and the Windows command line have the pipe operator (|), which can stream one command’s output (stdout) and send it to another command’s input (stdin). Let’s say you want to run all of your CSS first through Autoprefixer, then CSSMin, then output to a file (using the > operator, which outputs stdout to a given file):

```
"scripts": {
  "build:css": "autoprefixer -b 'last 2 versions' \< assets/styles/main.css | cssmin \> dist/main.css"
}
```

## Clean

Bash has a pretty good clean command all by itself: rm. Passing the -r (recursive) flag lets rm remove directories too! It couldn’t be simpler:

```
"scripts": {
  "clean": "rm -r dist/*"
}
```

## LiveReload


Now running npm run livereload - when you visit the HTML page it’ll start listening to the livereload server. Any changes to files in the dist/ directory will notifiy clients, and the page will be reloaded.

```
"devDependencies": {
  "live-reload": "latest",
},
"scripts": {
  "livereload": "live-reload --port 9091 dist/",
}
```

```
<!-- In your HTML file -->
<script src="//localhost:9091"></script>
```
