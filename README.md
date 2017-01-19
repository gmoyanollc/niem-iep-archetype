#Introduction
niem-iep-archetype is a [Maven Archetype](https://maven.apache.org/guides/introduction/introduction-to-archetypes.html) for developing a [National Information Exchange Model (NIEM) Information Exchange Package (IEP)](https://www.niem.gov/technical/Pages/Exchange-Assemble-And-Document.aspx).  

This Maven Archetype is nothing more than a template for consistently jump-starting NIEM development.  Once installed to a local Maven repository, it can be used again and again to generate a project folder with dependencies.  

The workflow is depicted below:
  ```
    /----------------------\
    |  niem-iep-archetype  |
    |    (installed in     |
    |      Maven repo)     |
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
  ```
##What's Included

* A folder tree that loosely resembles the guidance provided by NIEM 
  [Model Package Description (MPD)](https://reference.niem.gov/niem/specification/model-package-description/3.0/model-package-description-3.0.html#appendix_E). 

* Automation to add component 
  [niem-conformance-validator](https://github.com/gmoyanollc/niem-conformance-validator)

##Install to a Maven Repository
The following steps install the archetype to a local Maven repostiory:

1. Copy files or [git-clone](https://git-scm.com) this repository to a folder for projects:
  ```
      cd dev-project
      git clone  https://github.com/gmoyanollc/niem-iep-archetype
  ```    
Expected result:
  ```    
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
  ```
2. [Maven-install](https://maven.apache.org/download.cgi) this archetype to a Maven repository:
  ```
      cd niem-iep-archetype
      mvn clean install
  ``` 
Expected result:
  ```   
      ...
      [INFO] ------------------------------------------------------------------------
      [INFO] BUILD SUCCESS
      [INFO] ------------------------------------------------------------------------
      ...
  ```
3. Perform the following step to test the installation.

##Generate Project Folder with Dependencies
The following steps can be used again and again to generate a project folder with dependencies:

1. Generate a new project based on this archetype:
  ```
      cd dev-project
      mvn archetype:generate -DarchetypeCatalog=local

         Choose archetype:  "com.onename.gmoyano:niem-iep-archetype (niem-iep-archetype)"
         
         Enter a unique 'artifactId' property value.  This value determines the project's root folder name.
         
         Optionally accept property default values by pressing "Enter".
  ```
Expected result:
  ```  
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
  ```
2. Add external components using Ant, such as [niem-conformance-validator]( https://github.com/gmoyanollc/niem-conformance-validator)
  ```
      cd niem-iep
      ant
  ```
Expected result:
  ```    
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
  ```    
#Feedback
If you feel like the archetype is missing a feature or has a defect, contact me or create an [issue](https://github.com/gmoyanollc/niem-iep-archetype/issues). When creating a new issue, please provide a comprehensive description of your concern. Especially for fixing bugs it is crucial that I can reproduce your problem. For this reason, entire debug logs, source or most preferably little demo projects attached to the issue are very much appreciated. Of course, patches are welcome, too.

Copyright (c) 2016-2017 George Moyano (https://onename.com/gmoyano)

