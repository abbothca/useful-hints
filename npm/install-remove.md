## npm-link

First, npm link in a package folder will create a symlink in the global folder `{prefix}/lib/node_modules/<package>` that links to the package where the npm link command was executed. It will also link any bins in the package to '{prefix}/bin/{name}'.

Next, in some other location, `npm link package-name` will create a symbolic link from globally-installed **package-name** to **node_modules/** of the current folder.

```
npm link (in package dir)
npm link [<@scope>/]<pkg>[@<version>]
```

## Install

you can set these options in ~/.npmrc to update your defaults:
```
npm config set save=true
npm config set save-exact=true
cat ~/.npmrc
```

npm install saves any specified packages into **dependencies** by default. 
Additionally, you can control where and how they get saved with some additional flags:
-P, --save-prod: Package will appear in your dependencies. This is the default unless -D or -O are present.
-D, --save-dev: Package will appear in your devDependencies.
-O, --save-optional: Package will appear in your optionalDependencies.
--no-save: Prevents saving to dependencies.

When using any of the above options to save dependencies to your package.json, there are two additional, optional flags:
-E, --save-exact: Saved dependencies will be configured with an exact version rather than using npm's default semver range operator.
-B, --save-bundle: Saved dependencies will also be added to your bundleDependencies list.

## Remove

So sad to see you go.
```
sudo npm uninstall npm -g

npm uninstall lodash
```

For all:
```
rm -rf /usr/local/{lib/node{,/.npm,_modules},bin,share/man}/npm*

rm -rf node_modules/
```
