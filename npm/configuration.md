#Automating npm init Just a Bit More

When you're creating a new module from scratch, you'll typically start out with the npm init command. One thing that some developers don't know is that you can actually automate this process fairly heftily with a few choice npm config set ... commands that set default values for the npm init prompts.
You can easily set your name, email, URL, license, and initial module version with a few commands:

```bash
npm config set init.author.name "Hiro Protagonist"
npm config set init.author.email "hiro@showcrash.io"
npm config set init.author.url "http://hiro.snowcrash.io"
npm config set init.license "MIT"
npm config set init.version "0.0.1"
```
