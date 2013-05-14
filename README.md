# Introduction

This is a multi-module Maven project skeleton for a multi-module GWT project. This is mostly a note-to-self project but I hope that you can find it useful because it collects together, in a single place, several pieces of knowledge about Maven and GWT found scattered on the internet.

The project has separate modules for client, server and shared code, and provides a Web Application module for tying them all together.

The application is the one generated automatically by the Eclipse GWT Plugin when you create a new web application. To run it just do the following:

    mvn clean install
    cd maven-gwt-skeleton
    mvn gwt:run

## Importing the project into Eclipse

The prerequisite is that you have an Eclipse JEE installation with [M2Eclipse](http://eclipse.org/m2e/) and the [GWT Plugin](https://developers.google.com/eclipse/)

To import the project do the following:

* Import all the Maven project using `File->Import->Existing Maven projects...`. You can choose the top-level POM for importing everything.

* For every project, go to `Project->Properties->Build Path` and for every source folder make sure that the `Excluded` attribute is set to none. M2Eclipse sets this attribute to `**` by default on the `resources` paths, making the files there not visible in the classpath

* Make sure to add the `target-eclipse/generated-sources/gwt` as a source folder for the projects that automatically generates source code files. This is true, for example, for the `maven-gwt-skeleton-client` project.

* For every GWT project, setup GWT in `Project->Properties->Google->Web Toolkit` and `Project->Properties->Google->Web Application` (where applicable)

* For every project that has i18n messages, create a Run Configuration for generating i18n `Messages` classes. Use the following parameters:
** Main class: `com.google.gwt.i18n.tools.I18NSync`
** Program arguments: `-out ${workspace_loc:maven-gwt-skeleton-client}/src/main/java org.aqufi.client.Messages -createMessages`
** Add the `gwt-dev.jar` in the class path (you can find it in the bundled GWT SDK in Eclipse's `plugins` directory)

* In the Web Application project (e.g. `maven-gwt-skeleton-war`) add the other GWT projects as referenced projects in `Project->Properties->Build Path`

* Create a new `Web Application` Run Configuration, and to the default `VM Parameters` line append the GWT modules you want to host (e.g., `org.aqufi.GWTApp` and `org.aqufi.GWTAppClient`)

Enjoy.


