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

How to get started
------------------
1. [git-clone] (https://git-scm.com) this repository to a folder for projects:

        cd dev-project
        git clone  https://github.com/gmoyanollc/niem-iep-archetype
    
    Expected result:
    
        dev-project
        `-- niem-iep-archetype
            `-- src
                `-- main
                    `-- resources
                        |-- archetype-resources
                        |   `-- src
                        |       |-- main
                        |       |   |-- java
                        |       |   `-- resources
                        |       |       |-- application-info
                        |       |       |-- documentation
                        |       |       |-- iep-sample
                        |       |       |-- iep-schema
                        |       |       |   |-- extension
                        |       |       |   |-- external
                        |       |       |   `-- niem
                        |       |       |-- transform
                        |       |       `-- validate
                        |       |           `-- external
                        |       `-- test
                        |           `-- java
                        `-- META-INF
                            `-- maven

2. [Maven-install] (https://maven.apache.org/download.cgi) this archetype to a Maven repository:

        cd niem-iep-archetype
        mvn clean install
    
   Expected result:
   
        ...
        [INFO] ------------------------------------------------------------------------
        [INFO] BUILD SUCCESS
        [INFO] ------------------------------------------------------------------------
        ...

3. Generate a new project based on this archetype:

        cd dev-project
        mvn archetype:generate -DarchetypeCatalog=local

           Choose archetype:  "mil.usmc.mcsc.mctssa.tcg.iob:niem-iep-archetype (niem-iep-archetype)"
           
           Enter a unique 'artifactId' property value.  This value determines the project's root folder name.
           
           Optionally accept property default values by pressing "Enter".

    Expected result:
        
        ...
        [INFO] ------------------------------------------------------------------------
        [INFO] BUILD SUCCESS
        [INFO] ------------------------------------------------------------------------
        ...
        
        dev-project
        `-- niem-iep
            `-- src
                |-- main
                |   |-- java
                |   `-- resources
                |       |-- application-info
                |       |-- documentation
                |       |-- iep-sample
                |       |-- iep-schema
                |       |   |-- extension
                |       |   |-- external
                |       |   `-- niem
                |       |-- transform
                |       `-- validate
                |           `-- external
                `-- test
                    `-- java

4. add external components using Ant, such as niem-conformance-validator

        cd niem-iep
        ant
        
    Expected result:
    
        ...
        BUILD SUCCESSFUL
        ...
        
        ./src/test
        |-- java
        `-- resources
            `-- validate
                `-- validate-niem-conformance
                    `-- external
                        |-- iso-schematron-xslt2
                        |-- niem-ndr
                        `-- saxon
    
Feedback
--------
If you feel like the archetype is missing a feature or has a defect, contact me or create an [issue] (https://github.com/gmoyanollc/niem-iep-archetype/issues). When creating a new issue, please provide a comprehensive description of your concern. Especially for fixing bugs it is crucial that I can reproduce your problem. For this reason, entire debug logs, source or most preferably little demo projects attached to the issue are very much appreciated. Of course, patches are welcome, too.
//
// Updated by:
// Created by: George Moyano  Feb 2016
//