Introduction
------------
This is a [Maven Archetype] (https://maven.apache.org/guides/introduction/introduction-to-archetypes.html) for building a [National Information Exchange Model (NIEM) Information Exchange Package (IEP)] (https://www.niem.gov/technical/Pages/Exchange-Assemble-And-Document.aspx).  

This template contains folders and resources to jump-start development. 

How to use
----------
1. [git-clone] (https://git-scm.com) this repository in a empty target directory:

    git clone [resource]/niem-iep-archetype.git

2. [Maven-install] (https://maven.apache.org/download.cgi) this archetype to a Maven repository:

    mvn install

3. Generate a project based on this archetype in your development folder:

    mvn archetype:generate -DarchetypeCatalog=local

        Choose archetype:  "mil.usmc.mcsc.mctssa.tcg.iob:niem-iep-archetype (niem-iep-archetype)"

        Optionally accept property default values by pressing "Enter".  

        Enter a property 'artifactId' value.  The value determines the project's root folder name.
    
How to update
-------------

//
// Updated by:
// Created by: George Moyano  Feb 2016
//