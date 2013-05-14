# Introduction

This is a multi-module Maven project skeleton for a multi-module GWT project. This is mostly a note-to-self project but I hope that you can find it useful because it collects together, in a single place, several pieces of knowledge about Maven and GWT found scattered on the internet.

The project has separate modules for client, server and shared code, and provides a Web Application module for tying them all together.

The application is the one generated automatically by the Eclipse GWT Plugin when you create a new web application. To run it just do the following:

    mvn clean install
    cd maven-gwt-skeleton
    mvn gwt:run

You should also be able to import all of this back in an Eclipse environment and work from there using the Google GWT Plugin.

Enjoy.


