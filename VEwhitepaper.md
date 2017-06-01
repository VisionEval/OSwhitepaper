---
output: 
  html_document
bibliography: refs/vewhitepaper.bib
---

# Open Source Projects: Best Practices for VisionEval

*Draft*

This document outlines the proposed Best Practices whitepaper for the VisionEval project, regarding need for an open source approach to develop this collaborative research platform. 

Open source development of software provides a platform for software users and developers to engage in continuous improvement in a collaborative network. Collaboration via open source software development aligns with goals of public agencies involved in transportation planning, with a need to support freely-available decisionmaking tools which can be continuously improved by the user community.

[VisionEval](https://github.com/gregorbj/VisionEval) provides a framework for building collaborative, disaggregate strategic planning models. This open-source framework is the result of collaborations among partner agencies, namely the Federal Highway Administration (FHWA) and the Oregon Department of Transportation (OregonDOT). The VisionEval framework aims to support a broad array of potential uses, and thus will require a plan for incorporating software contributed by the user and developer community to extend the current functionality beyond the current modules. 
This paper provides an overview of best practices for open source software development for the VisionEval project. In particular, this paper outlines the process by which contributions will be evaluated and reviewed, and describes how version control and collaboration tools can be used to achieve this goal.

# Table of Contents
1. [Introduction](#introduction)
2. [Open Source Governance](#opensourcegovernance)
3. [Open Source Development](#opensourcedevelopment)
4. [Git and GitHub](#git)
4. [Summary](#summary)

## 1.	Introduction 

<!-- Discuss open source framework development of VisionEval, with an overview of best practices applicable to this project. -->

<!-- Brian Gardner Comment 2017-04-14
This enables a multi-year, collaborative research effort.
It is not a line of business IT system.
We will organize accordingly.

Draft Objectives for discussion
1)	 Maintenance of open access to research results to all parties through aggregated copyrights
2)	 Ability to build on prior research with clear copyrights
3)	 Enable collective action across sectors and participants while maintaining equal access
--> 

*	Define open source

Open source software projects are developed by Internet-based communities of software developers, who voluntarily collaborate their code to build a software tool for the public benefit [@VonKrogh2003]. Open source projects attract a user and development community which can spur innovation and novel applications beyond what the original developers may have envisioned [@Bettenburg2015], and so have become core parts of numerous commercial and non-commercial software projects.  


*	Intellectual property
    +	Maintenance of open access to research results for all parties through aggregated copyrights
    +	Ability to build on prior research with clear copyrights
*	Enable collective action across sectors and participants while maintaining equal access
*	Examples of successful open source projects (R, QGIS)

The 'openness' of open source projects is protected by copyrights such as the General Public License (GPL). The original GPL license, developed in the 1980's by the Free Software Foundation [@VonKrogh2003] ensured that those the right to use, study, modify, and distribute modified or unmodified code at no cost was preserved. Licences are key to preserving open source development, allowing users to contribute code without concerns that the code will be locked in a proprietary software in the future.

Software licenses can be chosen to reflect the needs of the project, using tools such as https://choosealicense.com/. The key elements of an open source license include the the following:

- Permission to modify code
- Permission to use commercially or privately
- Permission to distribute freely
- Attribution of authorship
- Limitations of liability and warranty
- Ability to patent the elements of code contributed
- Requirement that any derived code follow the license of the original code

The first three elements are common to all open source licenses. Attribution of authorship is typical, and ensures that derivative work based on the original code attributes the author. For example, the [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html) license states:

> <sub> You must retain, in the Source form of any Derivative Works that You distribute, all copyright, patent, trademark, and attribution notices from the Source form of the Work, excluding those notices that do not pertain to any part of the Derivative Works. </sub>

Patent protection is granted by some licenses, such as the Apache 2.0 license. This means that commercial ventures may contribute code to an open source project and still apply for a patent on that contributed code.  

For a research project such as VisionEval, a permissive license such as the [MIT license](https://choosealicense.com/licenses/mit/) would balance the need for preservation of copyright and attribution of authorship while promoting widespread use. 

## 2.	Open source governance <a name = "opensourcegovernance"></a>

-	Roles: Users, developers, administrators.
-	Resources ($) required, and how to obtain them

The distinction between commercial software projects and non-profit software projects provides a useful comparison for evaluating governance mechanism. The Android and Linux operating systems are both open source, but differ in their management of contributions from the community [@Bettenburg2015].

## 3.	Open source development   <a name = "opensourcedevelopment"></a>

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
-	Add Code - preparing for new version of RPAT
-	Add features, remove bugs
-	Document and release


Typical `git` workflow involves a single master repository. Developers can fork that repository, make modifications, and then push those modifications back to the master. To have separate workspaces for some users (contractors) than others, one solution would be to have two git repositories.


### Reviewing contributions from multiple sources

-	Role of the community of users
-	Gatekeeping versus crowdsource 
-	Merging branches, maintaining stable trunk

Unlike proprietary software project, open source research projects distinguish between a developer and user community. Contributions from the user community may be rare, typically limited to testing and bug reporting [@Aksulu2010]. Software code review by team members, however, typically follows well-established practice, with careful testing of software products early in the development cycle [@Thongtanunam2016]. The most formal realization of this type of code review involves developers meeting and reviewing printed-out code, line by line. Such review is impractical for large open source projects.

Instead, many open source software projects follow what has been dubbed Modern Code Review (MCR), and is often called a lightweight code review. This type of code review dominates in practice [@Beller2014].

While identifying defects is a core goal of code review, modern code review now also seeks to transfer knowledge, increase awareness, and create of alternative solutions to problems as well [@McIntosh2016].

GitHub and other online software repositories allow collaborative code review.

### Testing new contributions

-	Scenario testing
-	Model data sets
-	Compare output to prior model versions

### Documenting and Updating

-	Project background and user guides
-   Moving from beta to release versions
-	Documenting changes in release versions
-	Continuous work on development versions

## 4.	Git and GitHub  <a name = "git"></a>

Git is a distributed version control system. Git is *distributed* because every user has a complete copy of the repository. Git is a *version control system* in that it tracks the changes to files, allowing useful changes to be incorporated with attribution to the authors.


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

## 5.	Summary  <a name = "summary"></a>

-	Summarize best practices
-	Recommend practices and tools for the VisionEval team.
-	Next steps


# References
