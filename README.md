# Cloud Foundry

## Abstract

General set of notes for getting started with cloud foundry


## CF CLI installation {#cli}
NOTE: This info was obtained from [github.com/cloudfoundry/cli](https://github.com/cloudfoundry/cli#downloads)

For all platforms, 64-bit packages can be found 
[here](https://github.com/cloudfoundry/cli#installers-and-compressed-binaries)

#### NG Windows Desktop {#cli}
If you are on a NG desktop, you more than likely require the binaries zip file.
It contains a stand-alone binary that you should be able to run from your desktop

#### Linux Recommendation {#cli}
If you are on a Linux desktop, it is recommended to install the package provider 
so that your cf-cli is always up-to-date.  Instructions can be found
[here](https://github.com/cloudfoundry/cli#installing-using-a-package-manager)



## Logon to Cloud Foundry

Once installed, you can log in.  

~~~
For example:

$ cf login -a api.[my-cloudfoundry].com
API endpoint: https://api.[my-cloudfoundry].com

Email> [my-email]

Password> [my-password]
Authenticating...
OK
~~~

## Pushing Your App

Cloud Foundry will auto-detect dependencies for your app.

NOTE: For the most part.  You may require 3rd-party buildpacks
and other things which are beyond the scope of this document


~~~
$ cd [my-app-directory]
$ cf push
~~~

If the push is successful, a URL that can be used to access the 
web page where your app resides.

## Example App

Taking a look at [https://github.com/cloudfoundry-samples/hello-spring-cloud](https://github.com/cloudfoundry-samples/hello-spring-cloud) as 
a sample app.  

NOTES:

    * This is a maven app, so maven is needed on the systems
    * This is a git repo, best if git is installed
    * Obviously we need cf installed, see above
    * should be logged into cloud founder, see above

Steps:

* Clone the repo
    * git clone https://github.com/cloudfoundry-samples/hello-spring-cloud
* Build the app 
    * mvn clean package
* If successful maven build, push the app into cloudfoundry
    * cf push

