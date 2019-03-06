# 2019-03-06:

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
