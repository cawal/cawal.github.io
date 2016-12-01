---
layout: page
title: OBO & UML
permalink: /oboroeditor/
---

OBO-RO Editor
-------------

OBO-RO Editor is a Eclipse-based plugin/standalone editor that supports the creation of biomedical ontologies using the elements provided by a UML profile for the OBO Relation Ontology (`obo_rel`). This editor provides support for importing an OBO ontology represented using the OBO Flat File Format (OBOFFF) and for exporting a developed ontology as an OBOFFF ontology or as a shareable UML model.

We proposed a model-driven approach to support the development of a biomedical ontology using a UML profile for the OBO-RO and the integration between OBOFFF ontologies and UML models. According to this approach, different Ecore-based metamodels were created to represent an OBOFFF ontology and an OBO-RO profile-based biomedical ontology. Further, an existing Ecore-based metamodel was reused to represent a biomedical ontology as a UML shareable model. Different sets of ATL transformation modules were created to support the model transformation between these metamodels.




### Installing OBO-RO Editor as an Eclipse plugin
In your Eclipse Editor, "Window > Install new software...", add the the OBO-RO Editor Update Site at http://labs.cawal.com.br/update-sites/obo-ro-editor/ and install the OBO-RO Editor feature.


### Installing OBO-RO Editor as a Standalone Application

[Download OBO-RO Editor]()



OBO2UML transformation tool
---------------------------

OBO2UML is a command-line tool that supports the automatic transformation of an OBOFFF ontology into a shareable UML model.
OBO2UML allows one to quickly reuse the existing knowledge formalized in any OBO ontology represented using the OBOFFF for the creation of UML models that can be used in Model Driven Development Processes.


[Download the OBO2UML Executable JAR file](https://bitbucket.org/LSSB-FFCLRP/obo2uml/downloads/obo2uml.jar)

### OBO2UML Usage ###

```bash
# More than one OBO file can be used as input for the transformation
# The basic usage of OBO2UML is...
$ java -jar obo2uml.jar -i input1.obo [input2.obo ...] -o output.uml

# Example: Transforms the bone.obo ontology into a UML2 model
$ java -jar obo2uml.jar -i bone.obo -o bone.uml

# or you can use the long version...
$ java -jar obo2uml.jar --input-files bone.obo --output-file bone.uml

# You can also maintain the intermediary models files
$ java -jar obo2uml.jar --keep-files --input-files bone.obo --output-file bone.uml
```





Shareable UML Model Compatibility
---------------------------------

We represent ontologies as shareable UML models using the [Eclipse's Model Development Tools](http://www.eclipse.org/modeling/mdt/) [UML2 metamodel](http://wiki.eclipse.org/MDT-UML2). The compatibility of the obtained models with different UML-compliant tools can be verified in the MDT Wiki at [MDT-UML2-Tool-Compatibility](https://wiki.eclipse.org/MDT-UML2-Tool-Compatibility).


Contributing
------------
