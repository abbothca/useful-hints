# Using 'npm install' without Sudo

Npm packages installs should be done without sudo. Infact sudo should be never be used unless tinkering with system wide permissions. Node puts npm packages in a specific folder, usually /usr/local/lib/node_modules. But the trouble is you need sudo permissions to write here. This leads to an endless use of non-requisite sudo permissions. This location is what we need to change and here are handy terminal commands to achieve the same

```bash
mkdir ~/.npm

npm config set prefix ~/.npm

nano ~/.bashrc

export PATH="$PATH:$HOME/.npm/bin"

source ~/.bashrc
```

See guid [How to Prevent Permissions Errors](https://docs.npmjs.com/getting-started/fixing-npm-permissions)


# npm-init for short

If you invoke it with -f, --force, -y, or --yes, it will use only defaults and not prompt you for any options.
```bash
npm init --yes
```

# Automating npm init Just a Bit More

When you're creating a new module from scratch, you'll typically start out with the ** npm init ** command. One thing that some developers don't know is that you can actually automate this process fairly heftily with a few choice npm config ** set ... ** commands that set default values for the ** npm init ** prompts.

You can easily set your name, email, URL, license, and initial module version with a few commands:

```bash
npm config set init.author.name "Hiro Protagonist"
npm config set init.author.email "hiro@showcrash.io"
npm config set init.author.url "http://hiro.snowcrash.io"
npm config set init.license "MIT"
npm config set init.version "0.0.1"
```

# Changing the console output of npm install with loglevel

When you npm install a bunch of information gets piped to you. By default, the npm command line tool limits how much of this information is actually output into the console when installing. There are varying degrees of output that you can assign at install, or by default, if you change it with npm config in your .npmrc file. The options, from least to most output, are: silent, error, warn, http, info, verbose, and silly.

```bash
npm install express --loglevel silent
npm install express --loglevel warn
```

If you tinker around with this config a bit and would like to reset to what the npm CLI currently defaults to, you can run the above command with warn as the loglevel:
```bash
npm config set loglevel="error"
```
