## engines

You can specify the version of node that your stuff works on:
```
{ 
  "engines" : { 
    "node" : "~5.0.20" 
  } 
}
```

And, like with dependencies, if you don't specify the version (or if you specify "*" as the version), then any version of node will do.

You can also use the "engines" field to specify which versions of npm are capable of properly installing your program. For example:
```
{ "engines" : { "npm" : "~1.0.20" } }
```
Unless the user has set the engine-strict config flag, this field is advisory only and will only produce warnings when your package is installed as a dependency.
