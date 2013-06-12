HiveMind PM
===========

HiveMind PM is a project management application featuring task, request,
and content (wiki) management. There is support for multiple vendors,
multiple clients, flexible billing rates, time recording, and invoicing.

To run HiveMind you need Moqui Framework and Mantle Business Artifacts as
well as HiveMind itself. Moqui supports a few methods for setup and
deployment as described in the documentation here:

http://www.moqui.org/framework/docs/RunDeploy.html

To get the latest Moqui, Mantle, and HiveMind and run locally you'll need
JDK 1.6 or later, Gradle 1.6, and either a git client or you can use the
"ZIP" download links on each project page on github. The github project
pages are at:

https://github.com/jonesde/moqui
https://github.com/jonesde/mantle
https://github.com/jonesde/HiveMind

To download and run locally use the following steps:

1. Download Moqui Framework

Zip: https://github.com/jonesde/moqui/archive/master.zip
Git: git://github.com/jonesde/moqui.git

From either source you should have a "moqui" directory for the next steps.
If you use the Zip download change the directory name from "moqui-master"
to "moqui".

2. Download Mantle Business Artifacts

Zip: https://github.com/jonesde/mantle/archive/master.zip
Git: git://github.com/jonesde/mantle.git

Put the "mantle" directory in the "moqui/runtime" directory so it is
located at "moqui/runtime/mantle". If you use the Zip download change the
name of the directory from "mantle-master" to "mantle" to make sure the
directory under the "moqui/runtime" directory has the correct name.

3. Download HiveMind PM

Zip: https://github.com/jonesde/HiveMind/archive/master.zip
Git: git://github.com/jonesde/HiveMind.git

Put the "HiveMind" directory in the "moqui/runtime/component" directory so
it is located at "moqui/runtime/component/HiveMind". If you use the Zip
download change the name of the directory from "HiveMind-master" to
"HiveMind" to make sure the directory under the "moqui/runtime/component"
directory has the correct name.

4. Build and load seed and demo data

From the "moqui" directory run "gradle load".

This will build Moqui and load data from Moqui, Mantle and HiveMind into
an embedded Derby database.

5. Run Moqui

From the "moqui" directory run "gradle run".

6. Access the HiveMind application

In your browser go to:

http://localhost:8080/apps/hm

Use the button in the lower-left corner of the screen login as John Doe.

7. To use the search feature after an initial data load the indexing needs
to be run. After this ongoing changes are indexed automatically. The data
feed for search indexing is setup in database records, so they are not
present when records that should be indexed are initially loaded. To run
the index go to:

http://localhost:8080/apps/tools/DataDocument/Index

Select the the "HiveMind Search" data feed, leave the other fields empty,
and click on "Index Feed Documents". Now you can go to the Search screen
in HiveMind to search for Tasks, Projects, and Wiki Pages.
