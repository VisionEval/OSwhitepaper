---
output: 
  html_document
bibliography: refs/vewhitepaper.bib
---

# Open Source Projects: Best Practices for VisionEval

*Draft*

This document outlines the proposed Best Practices whitepaper for the VisionEval project, regarding need for an open source approach to develop this collaborative research platform. 

Open source development of software provides a platform for software users and developers to engage in continuous improvement in a collaborative network. Collaboration via open source software development aligns with goals of public agencies involved in transportation planning, with a need to support freely-available decisionmaking tools which can be continuously improved by the user community.

[VisionEval](https://github.com/gregorbj/VisionEval) provides a framework for building collaborative, disaggregate strategic planning models. These models are currently oriented towards providing easy-to use tools to visualize the impact of potential transportation policies, with the target audience being planners at state agencies and metropolitan planning organizations. The suite of modeling tools in the VisionEval framework includes the Regional Strategic Planning Model (RSPM), the Rapid Policy Assessment Tool (RPAT), and the Energy and Emissions Reduction Policy Analysis Tool ([EERPAT](https://www.planning.dot.gov/FHWA_tool/default.aspx)). 

This open-source framework is the result of collaborations among partner agencies, namely the Federal Highway Administration (FHWA) and the Oregon Department of Transportation (OregonDOT). The VisionEval framework aims to support a broad array of potential uses, and thus will require a plan for incorporating software contributed by the user and developer community to extend the current functionality beyond the current modules. 
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

*	Defining open source

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

The other distinction in governance structures is between centralized and decentralized projects. 

In a centralized open source governance structure, resources are dedicated to support a central gate-keeper.

<!-- A decentralized -->


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

Open source development relies on a community of developers to produce, evaluate, and integrate code into a project. There are a number ways that development can be organized in an open source framework, but the most important features are ability to incorporate existing code from other projects, ability to develop features independently, and agreed-upon methods for developers to share their additions with the community of other developers and users.

Incorporating code from other other projects is central to open source development. For example, the Vision California Urban Footprint project is an open-source scenario development and analysis tool for land use planning [(Hosted on GitHub)](https://github.com/CalthorpeAnalytics/urbanfootprint). This project drew from 12 distinct open source projects, including tools for database management, geospatial analysis, and data processing. The open source framework of this project has encouraged multiple users to 


best practices for open source development; the role of the developers in contributing additions and patches; best practices for reviewing code and maintaining working code base; testing code under new scenarios; documenting and updating. 

As development of the VisionEval models has been occurring for several years already, substantial content exists for each of the four models: (GreenSTEP, RPAT, RSPM, and EERPAT.

<!-- Open source projects build on ... -->

<!-- to incorporate previous work on modules such as RPAT, update that module, and release a new version. -->


### Workflow for VisionEval


Contributions to the VisionEval project ideally should follow the typical `git` work flow, using the GitHub web interface as described in detail below. In summary, the `git` workflow involves creation of a repository (folder of files) of the working version of the code, which is distributed across all the developers. The distributed nature of the repository means that developers can independently make modifications and additions to the code, and then request that this code be incorporated into the main version to be shared with all users.

The essential steps are as follows:
-	Establish repository - include RPAT work under AASHTO, previous versions of RPAT
-	Add Code - preparing for new version of RPAT
-	Add features, remove bugs
-	Document and release


### Reviewing contributions from multiple sources

-	Role of the community of users
-	Gatekeeping versus crowdsource 
-	Merging branches, maintaining stable trunk

Unlike proprietary software project, open source research projects distinguish between a developer and user community. Contributions from the user community may be rare, typically limited to testing and bug reporting [@Aksulu2010]. Software code review by team members, however, typically follows well-established practice, with careful testing of software products early in the development cycle [@Thongtanunam2016]. The most formal realization of this type of code review involves developers meeting and reviewing printed-out code, line by line. Such review is impractical for large open source projects.

Instead, many open source software projects follow what has been dubbed Modern Code Review (MCR), and is often called a lightweight code review. This type of code review dominates in practice [@Beller2014].

While identifying defects is a core goal of code review, modern code review now also seeks to transfer knowledge, increase awareness, and create of alternative solutions to problems as well [@McIntosh2016].

GitHub (see below) and other online software repositories allow collaborative code review.


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

### Git

Git is a distributed version control system. Git is *distributed* because every user has a complete copy of the repository. Git is a *version control system* in that it tracks the changes to files, allowing useful changes to be incorporated with attribution to the authors.

At the most basic level, Git manages version control for plain-text files, by tracking changes made at the level of each character in the file. For an individual developer working independently, this feature is already useful, replacing the manual 'version control' commonly done by adding "v2" or the date to a file name. In Git, the most current version of each file is kept, and a snapshot of the differences with previous versions is also kept. Those difference files allow users to examine previous versions of files 

Other version control software, such as Apache Subversion (SVN), achieve this type of tracking changes for individual files as well. The major difference between Git and other version control systems is the distributed aspect, as opposed to a centralized system. In a centralized version control system like SVN, there is a single master copy of a project. Each developer has to connect to that master copy, make changes to files individually, and then submit it back to the master copy. While one person is working on a file, no other user can edit it. For a small group working on a closed-source project, SVN and similar systems serve very well.

In a decentralized system, anybody can make a copy of the working version of a project ("clone" or "fork" it), work offline or otherwise disconnected from any central server. Multiple users can simultaneously work on projects, since each copy on users' computers is a complete version of the project. If a user has made some changes which they think are of interest to others, they can request that their changes be pulled back to the original. Git suits open-source projects very well, because of this decentralized system, and promotes collaboration among users from different organizations.

Other distributed version control systems exists, such as [Bazaar](http://bazaar.canonical.com/en/) and [Mercurial](https://www.mercurial-scm.org/). These have fewer users, but share many of the same features as Git. A major difference between Git and other systems is the number of users and the online platform for collaborating, GitHub.   

### GitHub

[GitHub](https://github.com) is the Internet platform supporting the use of Git. Git itself does not require the use of GitHub, as it can be used to track file versions on an a single computer. However, in nearly all instances users of Git are collaborating with others via GitHub. GitHub promotes collaboration by facilitating cloning repositories and creating pull requests (see below) to submit project improvements. The other major collaboration tools on GitHub are the presence of a wiki and the issue-tracking tools. 

Issue-tracking can be a powerful way for projects to engage users. The issue-tracking on GitHub provides a means for users to submit bugs or feature easily. Users submitting issues do not necessarily need to be developers with the time and ability to propose new code which solves those issues, simply users interested in improving the project. For example, an open-source data visualization project called Shiny has an active [issue tracking page](https://github.com/rstudio/shiny/issues), with some issues attracting multiple comments from other users, and discussion with the development team. In this case, the project is centralized in governance, with a software development company curating the project with input from users worldwide.

The wiki feature on GitHub is another tool which can both engage users and promote collaboration. Wikis can serve as the complete documentation for a project, at a detailed level. For example, the data visualization project d3 has an extensive and well-curated [wiki](https://github.com/d3/d3/wiki/Gallery), which provides a detailed introduction to the project and links to tutorials, examples, and active user groups.  Like other collaboratively modified web pages, the GitHub wiki tool allows collaborators to make page improvements. However, unlike public wikis such as Wikipedia, collaborators must be identified by the repository owner to be given permission to make edits.

###	Pull requests

Git development is also called pull-based development. The "pull" refers to pulling changes from individual users. On GitHub, original creator of a repository is the 'owner', and by default the owner is the only user with the ability to merge pull requests from other contributors. This type of collaboration suits open source projects well, as occasional contributions from users can be vetted by the project team, and accepted, rejected, or have further changes proposed.  

This code review process is done on GitHub. While the core team is developing a project, at any time a user can fork a repository, make edits, and then create a pull request. The core team then inspects the changes made by the pull request, and can discuss on GitHub the merits of what the changes would accomplish. In some cases, the core team (composed of the repository owner and collaborators) may ask users to make further changes to their code before accepting the pull requests. On acceptance, the code from the user is merged into project.  

Only a small proportion of projects on GitHub use pull requests, with 14% of project as of 2016 found to have active pull requests [@Gousios2014]. Core team members can make changes by directly committing to the project, and many projects are driven by the core team only. These projects may still be forked and used by others, but are not attracting suggestions for improvement from the user community. 
The majority of pull requests on GitHub projects are for small changes (10 lines of code), attract a small number of comments, and are made by developers who have made a few dozen other pull requests across all GitHub projects. Most pull requests are merged with 4 days of creation [@Gousios2014], demonstrating the rapid pace of development supported by GitHub.

### Documenting changes
 
Documentation of open source projects occurs at both the small and large scale. At the small scale, every change made by commits to a project or via pull requests need to be documented. Every commit on Git requires a short message to document the specific change, and pull requests are documented by the Pull Requests tab on a GitHub page. At a larger scale, developers need to provide documentation about how to use the tools, which is done in both a brief README file and ideally in greater detail on the GitHub wiki. For some projects, a separate PDF file may exists as the project documentation, but such a static file may not serve the needs of an actively-developing project. For active projects, a wiki should serve as the complete documentation.

Major updates to projects may be documented by creating a release, which has a version number and brief notes to document the significant changes. Releases provide a way to mark major changes to the software tools. Since users are not downloading executable files in the traditional method of releasing software, the GitHub releases are simply milestones marking points that the core team has decided are significant changes, and can provide static snapshots of the project at that time. An example of an R package of analysis tools used by biologists [here](https://github.com/vegandevs/vegan/releases) shows how the source code for specific releases is bundled into archive files, with extensive documentation. 


### Communicating with the user community

Successful projects have a community of users who employ and improve the tools of the project. Users can become engaged in the project by contributing suggestions via the issue-tracking tool on GitHub, or directly contributing improvements project with pull requests. However, one common method of engaging users not supported by GitHub is a forum for users to ask general questions and share knowledge. Such forums are used distribution platforms such as the [Open Source Application Development Portal](https://www.itsforge.net/index.php/community/discussion-forum) of the Federal Highway Administration, or on individual project web pages, such as the [UrbanSim](http://discussion.urbansim.com/) project for planning and analysis of urban development. User forums of a sort also exist outside of official project web pages, for example on the highly active Stack Overflow site. This site which allows developers to ask and answer questions about specific problems with a tool, or more issues more general than one tool. A forum can be developed for a GitHub Pages site, which is a way to host a front-end website for a GitHub project.

For projects such as VisionEval which will likely have a small number of specialized users, a discussion forum may not be the most beneficial tool. Instead, using Issues on GitHub likely will present the best way for users to discuss specific technical topics about VisionEval tools. As users of VisionEval tools will be technically sophisticated enough to know about and use GitHub, keeping the online discussion on the GitHub pages will be the most convenient way to host discussions.

In addition to online discussions, periodic announcements by email can be useful. Such announcements may be on at regular periods, or following releases of major updates or new modules. Maintaining a list of interested users would require some investment of effort for the centralized governing organization. Large open source projects with many active users do not typically have email announcements, but for VisionEval such announcements could be useful for engaging the community of users who are not developers. 


<!-- general SO example: https://gis.stackexchange.com/questions/68349/are-there-open-source-solutions-for-travel-demand-modelling -->
<!-- Disqus forum for GitHub pages: http://klcodanr.github.io/Jekyll-Disqus-Forum/ -->

## 5.	Summary  <a name = "summary"></a>

-	Summarize best practices
-	Recommend practices and tools for the VisionEval team.
-	Next steps


# References
