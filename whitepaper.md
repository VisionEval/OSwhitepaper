# Open Source Projects: Best Practices for VisionEval

Draft

This document outlines the proposed Best Practices whitepaper for the VisionEval project, regarding need for an open source approach to develop this collaborative research platform. 

## 1.	Introduction 

<!-- Brian Gardner Comment 2017-04-14
This enables a multi-year, collaborative research effort.
It is not a line of business IT system.
We will organize accordingly.

Draft Objectives for discussion
1)	 Maintenance of open access to research results to all parties through aggregated copyrights
2)	 Ability to build on prior research with clear copyrights
3)	 Enable collective action across sectors and participants while maintaining equal access
--> 

Discuss open source framework development of VisionEval, with an overview of best practices applicable to this project.

*	Define open source
*	Intellectual property
    +	Maintenance of open access to research results for all parties through aggregated copyrights
    +	Ability to build on prior research with clear copyrights
*	Enable collective action across sectors and participants while maintaining equal access
*	Examples of successful open source projects (R, QGIS)

## 2.	Open source governance

-	Roles: Users, developers, administrators.
-	Resources ($) required, and how to obtain them

## 3.	Open source development  

<!-- Brian Gardner Comment 2017-04-14
We will need to accomplish in the initial phase
1)	 uptake of the AASHTO contract work on RPAT
2)	 Host the prior versions of RPAT
3)	 Release a new major version
4)	 Make at least one maintenance release

5)	 Define a relationship or uptake the ODOT sponsored work

Let's use these tasks to test initial procedures and repository organizations, with input from ODOT on TLUMIP. 

Lean on:
http://stackoverflow.com/documentation/git/topics
-->

Discuss the best practices for open source development; the role of the developers in contributing additions and patches; best practices for reviewing code and maintaining working code base; testing code under new scenarios; documenting and updating. This section will also propose procedures for VisionEval to incorporate previous work on modules such as RPAT, update that module, and release a new version.

### Workflow for VisionEval

-	Follow GitHub procedures outlined below for version control and collaboration
-	Establish repository - include RPAT work under AASHTO, previous versions of RPAT
-	Add Code - preparing for new version of RPAT.
-	Add features, remove bugs
-	Document and release

### Reviewing contributions from multiple sources

-	Role of the community of users
-	Gatekeeping versus crowdsource 
-	Merging branches, maintaining stable trunk

### Testing new contributions

-	Scenario testing
-	Model data sets
-	Compare output to prior model versions

### Documenting and Updating

-	Moving from beta to release versions
-	Documenting changes in release versions
-	Continuous work on development versions

## 4.	Git and GitHub

Discuss Git as a specific tool for version control and collaboration, to accomplish the workflow established above.

-	Version control in Git
    +	Master branch
    +	Development branches
    +	Merging with pull requests
    +	Documenting changes
-	Comparison with other tools: Apache Subversion (SVN), Mercurial (Hg), Bazaar
-	Discuss web-based project management using GitHub, with issue tracking and wikis.
-	Discuss user group engagement via listservs. 
  +	Developer listserv 
  +	User listserv

## 5.	Summary

-	Summarize best practices
-	Recommend practices and tools for the VisionEval team.
-	Next steps

