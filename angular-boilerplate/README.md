Overview
========

The structure of the repository is outlined below
------------------------------------

* README.md
* Ant build file
* Sample build and properties files
* lib: contains the ant-salesforce.jar file and other script files so that developers do not need to download themselves
* src: contains the Force.com source files, structred in alignment with the folder structure returned by the Ant sfretrieve task.
* src/removecode: contains a destructiveChanges.xml file that is used to remove objects.


Running the ANT tasks locally
------------------------------------

First, ensure that you have a build.properties in the repo root with the proper credentials for the environment you want to pull or push to.

The current build.xml options:

pushAll: Looks at the src/package.xml and deploys all assets.
retrieveUnpackaged: Looks at the src/package.xml and retrieves all assets.
undeployCode: Looks at the src/removecode/destructiveChanges.xml and removes all assets identifed there.

You can invoke locally using the following three commands:

ant -propertyfile build.properties pushAll

ant -propertyfile build.properties retrieveUnpackaged

ant -propertyfile build.properties undeployCode

Note: The propertyfile parameter is needed in case if you intend to use a CI with Jenkins.
