## Set init data

You can also set several config options for the init command. Some useful ones:
```
npm set init.author.email "wombat@npmjs.com"
npm set init.author.name "ag_dubs"
npm set init.license "MIT"
```

you can set these options in ~/.npmrc to update your defaults:
```
npm config set save=true
npm config set save-exact=true
cat ~/.npmrc
```

## config

A "config" object can be used to set configuration parameters used in package scripts that persist across upgrades. For instance, if a package had the following:
```
{ 
  "name" : "foo",
  "config" : { 
    "port" : "8080",
    "somevar" : "some text" 
  } 
}
```
and then had a `"start"` command that then referenced the **npm_package_config_port** or **npm_package_config_somevar** environment variable.

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
