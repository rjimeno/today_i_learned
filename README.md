# 2019-04-21:

CFEngine seem to be the first modern or contemporary Configuration
Management tool.

I found very interesting information for it on
Wikipedia although there is currently a warning there regarding
single-source information.

Finally, I need to find time to read the 1998 paper [Computer
Immunology](https://www.usenix.org/legacy/publications/library/proceedings/lisa98/full_papers/burgess/burgess.pdf)
(from a Usenix's LISA conference) as it seem to be important.


# 2019-03-17:

GDB does not run on a Apple's OS X until after you have "codesigned"
it. One way to go about that is described in the following URL:
https://gist.github.com/hlissner/898b7dfc0a3b63824a70e15cd0180154

The instructions that follow here are copied from there:
> Note: these instructions are for pre-Sierra MacOS. Sierra Users: see
https://gist.github.com/gravitylow/fb595186ce6068537a6e9da6d8b5b96d 
by @gravitylow.

If you are getting this in gdb on OSX while trying to run a program:

```bash
Unable to find Mach task port for process-id 57573: (os/kern) failure (0x5).
 (please check gdb is codesigned - see taskgated(8))
```

1. Open Keychain Access
2. In the menu, open **Keychain Access > Certificate Assistant > 
Create a certificate**
3. Give it a name (e.g. `gdbc`)
    + Identity type: Self Signed Root
    + Certificate type: Code Signing
    + Check: let me override defaults
4. Continue until it prompts you for: "specify a location for..."
5. Set Keychain location to System
6. Create a certificate and close assistant.
7. Find the certificate in System keychains, right click it > get 
info (or just double click it)
8. Expand **Trust**, set **Code signing** to `always trust`
9. Restart taskgated in terminal: `killall taskgated`
10. Enable root account:
    1. Open System Preferences
    2. Go to User & Groups > Unlock
    3. Login Options > "Join" (next to Network Account Server)
    4. Click "Open Directory Utility"
    5. Go up to **Edit > Enable Root User**
11. Run `codesign -fs gdbc /usr/local/bin/gdb` in terminal: this asks 
for the root password
12. Disable root account (see #10)

Done!


# 2019-03-15:

Udacity's [Computer Networking by Georgia Tech (UD436) Security and Software Defined Networking](https://www.udacity.com/course/computer-networking--ud436) is an excelent course!

Personally, I reviewed a lot of material that I forgot about Computer Networking back from my days as a student and I also learned a few things that are new or have developed relevance within the past decade.


# 2019-03-05:

```Jenkinsfile
#!/usr/bin/env groovy

// Jenkins Scripted Pipeline by Roberto Jimeno shows a way to get tomorrow's date and use it from Groovy.

// The core of this trick is to use “date -d '+1 day'” to get tomorrow’s date on Gnu systems (v.g. Linux) or “date -v+1d” many
// other systems (like OS X, e.g.).

// Following pair of environment variables will be used later.
env.utc_today=
env.utc_tomorrow='' 

// This post_alarm() function is not really necessary, but shows formatting ISO style.
def post_alarm(body) {
    String data = dataForCurl(body, '')

    sh """
        iso_today=\$(date -u +%Y-%m-%dT%H:%M:%S.000Z)
        iso_tomorrow=\$(date -d “+1 day” -u +%Y-%m-%dT%H:%M:%S.000Z)
    """
}

node {
    stage('Create time stamp.') {
        env.utc_today = sh (
                script: 'date -u +%Y%m%d%H%M%S',
                returnStdout: true
        ).trim()
        env.utc_tomorrow = sh (
                script: 'date -d “+1 day” -u +%Y%m%d%H%M%S',
                returnStdout: true
        ).trim()
        println $env.utc_today
        println $env.utc_tomorrow
        sh "date -u +%Y%m%d%H%M%S > TODAY.txt"
        sh "date -u +%Y%m%d%H%M%S > TOMORROW.txt"
    }
}
```

# 2019-02-22:

On a Mac (running OS X or MacOS), Vagrant can be installed using
Homebrew using the following command:

$ brew cask install vagrant

The 'brew install' commands without 'cask' tipically installs somewhat
simple, command-line software distributed under some FOSS license. In
contrast, 'brew cask install' commands can be used to install more
complex software, that has or interacts with a GUI and that is
licensed under some form of proprietary license.


# 2019-02-21:

By accident, I came accross the executable binary file
/usr/bin/sigdist.d on my Mac and that lead me to 'man sigdist.d' which
in turn sent me to Safari Books Online for the book DTrace: Dynamic
Tracing in Oracle and so I'm beginning to lear that DTrace is a
powerful tool that can help me performance-tune software and systems.

Just put a bunch of material in a queue and I'll start reading once I
have some availability.
