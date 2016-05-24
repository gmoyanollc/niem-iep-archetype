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
    
    * Automation to add component [niem-conformance-validator] ( https://github.com/gmoyanollc/niem-conformance-validator )

How to use
----------
1. [git-clone] (https://git-scm.com) this repository:

    git clone  https://github.com/gmoyanollc/niem-iep-archetype
    
    Expected result:
    
        niem-iep-archetype
        |-- src
        `-- target

2. [Maven-install] (https://maven.apache.org/download.cgi) this archetype to a Maven repository:

    mvn clean install

3. Generate a project based on this archetype in your development folder:

    mvn archetype:generate -DarchetypeCatalog=local

        Choose archetype:  "mil.usmc.mcsc.mctssa.tcg.iob:niem-iep-archetype (niem-iep-archetype)"

        Optionally accept property default values by pressing "Enter".  

        Enter a unique 'artifactId' value.  This value determines the project's root folder name.
        
4. 
    
Feedback
--------
If you feel like the archetype is missing a feature or has a defect, contact me or create an [issue] (https://github.com/gmoyanollc/niem-iep-archetype/issues). When creating a new issue, please provide a comprehensive description of your concern. Especially for fixing bugs it is crucial that I can reproduce your problem. For this reason, entire debug logs, source or most preferably little demo projects attached to the issue are very much appreciated. Of course, patches are welcome, too.
//
// Updated by:
// Created by: George Moyano  Feb 2016
//