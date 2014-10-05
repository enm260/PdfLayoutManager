PdfLayoutManager
================
A page-layout manager for PDFBox to do things like line-breaking, page-breaking, and tables.
Uses a box-model for styles.
Requires PDFBox which in turn requires Log4J or apache commons Logging.

Usage Example
=============
The unit tests may be monolithic, but they provide a good usage example:

https://github.com/GlenKPeterson/PdfLayoutManager/blob/master/src/test/java/com/planbase/pdf/layoutmanager/TestPdfLayoutMgr.java


Building from Source
====================
Requires Maven 3 and Java JDK 1.5 or greater (earliest verified JDK is: 1.6.0_45).  Jar file ends up in the `target/` sub-folder.

API documentation can be built with `mvn javadoc:javadoc` and is then found at `target/site/apidocs/index.html`

A sample PDF named `test.pdf` shows up in the root folder of this project when you run `mvn test`.

A jar file can be built with `mvn clean package` and ends up in the `target/` sub-folder.

Recent Changes
==============
Version 0.2.1: Built with JDK 1.6.0_45 to ensure backward compatibility (Maven 3 wouldn't run with 1.5.0_22).
Made a few classes private and updated the JavaDocs.

Version 0.2: Added true table builder classes, a cascade of styles from Document to LogicalPage to Renderable/Cell/Table, etc.
Tables have Parts (which you probably will define as a head and body with appropriate styles and column widths).
TableParts have Rows, Rows have Cells.
Cells are also Renderable and available outside of Tables, analogous to the HTML box-model, but without "margins" only padding and borders.
Also added PNG image support.

Version 0.1.1: Added run-time check for appropriate data types used to create a Cell to provide fail-fast behavior for
client code - if you pass an invalid object type, it throws an exception immediately instead of waiting to purge the cache.

Version 0.1: Initial working and documented version

License
=======
Copyright 2013 PlanBase Inc. and Glen Peterson

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
