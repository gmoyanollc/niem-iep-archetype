Introduction
------------
This is a [Maven Archetype] (https://maven.apache.org/guides/introduction/introduction-to-archetypes.html) for building a [National Information Exchange Model (NIEM) Information Exchange Package (IEP)] (https://www.niem.gov/technical/Pages/Exchange-Assemble-And-Document.aspx).  

    /----------------------\
    |  niem-iep-archetype  |
    |                      |
    \----------------------/
                |
                V 
        /--------------\
       /     Maven      \
      /     generate     \
      \------------------/
                |
                V 
      /------------------\
      |  my-iep-project  |
      |                  |
      \------------------/

The intent of this template is to jump-start the development of a NIEM-specified IEP.

Contents
--------

    * A folder tree that loosely resembles the guidance provided by NIEM [Model Package Description (MPD)] (https://reference.niem.gov/niem/specification/model-package-description/3.0/model-package-description-3.0.html#appendix_E). 
    
    * ISO Schematron validators in XSLT2

    * Ant Task for Schematron with SVRL and text output
    
    * NIEM Naming and Design Rules (NDR) 3.0 2014 Schematron

How to use
----------
1. [git-clone] (https://git-scm.com) this repository to an empty target directory:

    git clone [resource]/niem-iep-archetype.git

2. [Maven-install] (https://maven.apache.org/download.cgi) this archetype to a Maven repository:

    mvn install

3. Generate a project based on this archetype in your development folder:

    mvn archetype:generate -DarchetypeCatalog=local

        Choose archetype:  "mil.usmc.mcsc.mctssa.tcg.iob:niem-iep-archetype (niem-iep-archetype)"

        Optionally accept property default values by pressing "Enter".  

        Enter a property 'artifactId' value.  The value determines the project's root folder name.
    
Feedback
--------
If you feel like the archetype is missing a feature or has a defect, contact me or create an [issue] (https://github.com/gmoyanollc/niem-iep-archetype/issues). When creating a new issue, please provide a comprehensive description of your concern. Especially for fixing bugs it is crucial that I can reproduce your problem. For this reason, entire debug logs, source or most preferably little demo projects attached to the issue are very much appreciated. Of course, patches are welcome, too.
//
// Updated by:
// Created by: George Moyano  Feb 2016
//