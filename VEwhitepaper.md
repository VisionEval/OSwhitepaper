---
title: 'Open Source Projects: Best Practices for VisionEval'
author: "| Dan Flynn \n| Volpe Center \n| daniel.flynn.ctr@dot.gov"
output:
  word_document: default
  pdf_document: default
  html_document: default
bibliography: refs/vewhitepaper.bib
---

*Draft*

# Summary

This document outlines the proposed Best Practices whitepaper for the VisionEval project, regarding need for an open source approach to develop this collaborative research platform. 

Open source development provides a platform for users and developers to engage in continuous, collaborative improvement of software tools. Collaboration via open source software development aligns with goals of public agencies involved in transportation planning, with a need to support freely-available decisionmaking tools which can be continuously improved by the user community and widely disseminated to promote effective transportation planning.

[VisionEval](https://github.com/gregorbj/VisionEval) is an open source framework for building collaborative, disaggregate strategic planning models for transportation planners. These models are currently oriented towards providing easy-to use tools to visualize the impact of potential transportation policies, with the target audience being planners at state agencies and metropolitan planning organizations. The suite of modeling tools in the VisionEval framework includes  [GreenSTEP](http://www.oregon.gov/ODOT/Planning/Documents/GreenSTEP-Model-Overview.pdf), the Regional Strategic Planning Model ([RSPM](https://github.com/gregorbj/RSPM)), the Rapid Policy Assessment Tool ([RPAT](https://github.com/gregorbj/VisionEval)), and the Energy and Emissions Reduction Policy Analysis Tool ([EERPAT](https://www.planning.dot.gov/FHWA_tool/default.aspx)). 

This open-source framework is the result of collaborations among partner agencies, namely the Federal Highway Administration (FHWA), the Oregon Department of Transportation (OregonDOT), and the American Association of State Highway and Transportation Officials (AASHTO). The VisionEval framework aims to support a broad array of potential uses, and thus will require a plan for incorporating software contributed by the user and developer community to extend the current functionality beyond the current modules. This paper provides an overview of best practices for open source software development for the VisionEval project. In particular, this paper outlines the process by which contributions will be evaluated and reviewed, and describes how version control and collaboration tools can be used to achieve this goal.

# Table of Contents
1. [Introduction](#introduction)
2. [Open Source Governance](#opensourcegovernance)
3. [Open Source Development](#opensourcedevelopment)
4. [Git and GitHub](#git)
5. [Recommendations](#summary)

## 1.	Introduction 

<!-- Discuss open source framework development of VisionEval, with an overview of best practices applicable to this project.
Draft Objectives for discussion
1)	 Maintenance of open access to research results to all parties through aggregated copyrights
2)	 Ability to build on prior research with clear copyrights
3)	 Enable collective action across sectors and participants while maintaining equal access
--> 

Open source software projects are developed by Internet-based communities of software developers, who voluntarily collaborate their code to build a software tool for the public benefit [@VonKrogh2003]. Open source projects attract a user and development community which can spur innovation and novel applications beyond what the original developers may have envisioned [@Bettenburg2015], and so have become core parts of numerous commercial and non-commercial software projects.  In the public sector, open source approaches have become the common in agencies as diverse as the [Department of Defense](http://dodcio.defense.gov/Open-Source-Software-FAQ/), [NASA](https://github.com/nasa/open-source-catalog), and the [Consumer Financial Protection Bureau](http://cfpb.github.io/source-code-policy/). 

Governmental users and organizations on open source collaboration platforms have been growing [exponentially](https://github.com/blog/1874-government-opens-up-10k-active-government-users-on-github), and the platform GitHub has established a site to facilitate the incorporation of open source principles to governmental software development [(government.github.com)](https://government.github.com/). For public agencies, major benefits of adopting these approaches to software development include the transparency, cost-effectiveness, and longevity of open source tools.  

Transparency in open source development is achieved because code is readily available to the community of users. This promotes accountability and reproducibility of research projects, beyond what can be achieved even by peer-review of a journal article. Some researchers argue that the element of transparency also promotes innovation, as modules of code can be reviewed and built on, spurring rapid development of tools in as areas such as information systems [@von2007open] and weather station monitoring [@Heistermann2015]. 

Cost-effectiveness comes from the ability to build on common tools. For example, the software [QGIS](http://www.qgis.org/en/site/) is an open source geospatial modeling and visualization tool, and builds on a large number of modules written in the programming language Python. Users can add modules for their own specific needs, and an active community of users discusses these suggested modifications and decides how to incorporate them into the project. Such cost-effectiveness means that the software tool is free and constantly improving. The free availability of this spatial analysis tool has made QGIS popular, for instance, with water resource managers in developing countries [@chen2010assessment]. 

Longevity arises from the fact that the code is developed in a community effort. As it is not tied to a single individual, the code can continue to be maintained and supported by the community. Provided the community exceeds a certain size, the project can be resilient to changes in the involvement of individual developers [@Heistermann2015]. For public agencies, this longevity avoids lock-in with a single vendor [@zhu2012research].

A crucial factor underpinning these benefits is the licensing that protects open source software. The 'openness' of open source projects does not mean that they have no license; open source software is protected by copyrights such as the General Public License (GPL). The original GPL license, developed in the 1980's by the Free Software Foundation [@VonKrogh2003] ensured that the right to use, study, modify, and distribute modified or unmodified code at no cost was preserved. Licences are key to preserving open source development, allowing users to contribute code without concerns that the code will be locked in a proprietary software in the future. 

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

For a research project such as VisionEval, a permissive license such as the [MIT license](https://choosealicense.com/licenses/mit/) or [Apache 2.0 license](https://choosealicense.com/licenses/apache-2.0/) would balance the need for preservation of copyright and attribution of authorship while promoting widespread use. The former is more permissive, while the latter adds grant of patent rights, and adds the requirement that changes to the code must be stated. 

An additional layer of licensing can be used to ensure that contributions to a project fall within the license of the project. Contributor License Agreements ([CLAs](https://www.clahub.com/pages/why_cla)) ensure that when a project accepts contributions from a third party, all necessary copyrights to release the code are in place. A CLA can provide extra assurance the governing organization of a project has all the appropriate permissions to incorporate patches or improvements to the project, and distribute the resulting work. A CLA may be unnecessary for open source project where concerns about patent or copyright infringement are minimal, and is mostly useful when a for-profit company submits patented code to an open-source project. For a project such as VisionEval, a CLA likely is not essential.    

## 2.	Open source governance <a name = "opensourcegovernance"></a>

Achieving these benefits of open source tools requires a governance structure. There are multiple models of governance for open source projects. The distinction between commercial software projects and non-profit software projects provides a useful comparison for evaluating governance mechanism. The Android and Linux operating systems are both open source, and share an overall similar structure of how code is reviewed, with some crucial differences [@Bettenburg2015]. 

Common to both approaches, suggestions are reviewed by the community to assure quality, determine fit of the contribution to the project, and sanitize code. If the code is considered a worthy addition to the project, the code will be accepted into the main project repository. This process is explained in detail in the Open Source Development section, and is outlined in the figure below.

![Conceptual model of the collaboration management process (Bettenburg et al. 2015).](https://raw.githubusercontent.com/VisionEval/OSwhitepaper/master/images/Bettenburg_Fig1.JPG "Content Review Process")

For both commercial and non-commercial open source projects, this same work flow is followed, with the distinction being the identity of the contributors and degree to which outside contributions are accepted into the code base.

The commercial Android software is developed by Google and distributed freely, with the core software developed by programmers supported by Google. Phone hardware manufactures can modify the Android software to tailor it to their devices, and users can submit modifications to be integrated into the core software, acting as Contributors in the process above. Contributors are required to agree to a Contributor License Agreement (CLA, see above) to transfer intellectual property rights to Google. This is a centralized project, with staff supported by Google to review code, who act to implement the Review, Verification, and Integration steps.

For the non-commercial Linux operating system, no CLA is required for contributors. This large, decentralized project has many contributors and many reviewers, without a single review team. The difference between centralized and decentralized projects has been likened to the difference between a 'cathedral' and a 'bazaar' [@raymond1999cathedral]. The 'bazaar' style of Linux means that new ideas are constantly being shared and reviewed, far more than any one team could manage to review. Commercial software and smaller teams typically take more of a 'cathedral' style development process, where only core group of developer have the authorization to commit changes to the central repository. 

Further examples of governance structures for code review follow below. These examples highlight the differences between large projects where many modules are being developed in an experimental fashion, with bazaar-style exchange of ideas and multiple versions, versus smaller projects curated in a cathedral-style fashion. For VisionEval, maintaining a balance between 'cathedral' and 'bazaar' style development will be essential to encourage users to be active in experimenting with new modules, while maintaining a functional and stable code base.

#### Example large project: `Node.js`

For a large open source project, extensive community engagement and a clear governance structure is essential. Node.js is a JavaScript tool for event-driven web programming. The community is organized into groups of Users, Collaborators, and Leaders. The number of users is vast, at least in the tens of thousands. At the leadership level, there is a Core Technical Committee (CTC) of approximately 20 members. Additional Working Groups exist for to manage security, specific technical issues, and releases. 

Users can most easily become involved in this coding effort by contributing issues on the project GitHub page, where over 5,000 issues have been submitted. If users decide to contribute a new feature or propose a bug fix, they can open a pull request. Over 8,000 pull requests have been opened for Node.js, with some receiving comments from over 100 users or Collaborators. An extensive documentation of [development guidelines](https://nodejs.org/en/get-involved/development/) exists. These guidelines specify, among other issues, that contributors state a "Certificate of Origin" which acts similarly to a CLA to ensure that contributions will remain public and under the license of the project itself.

Users become Collaborators by being identified by the CTC as someone who has made [signfificant and valuable contributions](https://github.com/nodejs/node/blob/master/GOVERNANCE.md) to the project. Collaborators review contributions of code, help other collaborators, and have commit rights to merge pull requests. The Core Technical Committee has oversight of the activities of the collaborators. 

The CTC membership is handed out by existing CTC members, at one of the weekly meetings that occurs. A unique feature of the Node.js governance is that no more than 1/3 of the CTC members may be affiliated with the same employer. Decisions are made by ["Consensus Seeking"](https://en.wikipedia.org/wiki/Consensus-seeking_decision-making) process, whereby if the CTC cannot come to consensus on an issue, it can either be tabled or put forward for a vote by simple majority.

Community engagement is extensive, with a web chat channel, Twitter account, weekly newsletter, podcast, and many web resources. User groups exist in many languages, and documentation exists in many forms. These community engagement efforts are key to helping new users learn about the tool and become proficient. While VisionEval will not likely reach the same scale of adoption, the clear structure used by this mature open source project provides a model to examine while considering a governance structure.

#### Example small project: `vegan`

`vegan` is a popular package of R tools for ecologists, with a focus on analysis of vegetation data. There are on average 800 weekly downloads of the package, and thousands of users. The package was developed originally by a single academic researcher, and now has 16 active contributors, and has been forked over 30 times. With vastly smaller scale than Node.js, this community of developers has not developed any formal governance structure, apparently relying on informal email communication between developers to coordinate pull requests. 

Some of the [documentation](http://vegan.r-forge.r-project.org/FAQ-vegan.html) of `vegan` is maintained by the single original developer, with the package itself containing documentation vetted by the contributors. The package is licensed under [GPL-2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html), a fairly permissive copyleft license. This license or similar is recommended for scientific research projects [@Wilson2017], allowing reuse in commercial or noncommerical settings. Other than the license, this project lacks any formal governance structure, which may be common for open source projects which were designed by single users, even with a relatively large base of users.

While this structure clearly works for a tool with an active academic group of users, VisionEval should strive to establish a clear governance structure which lays out roles and responsibilities of users, contributors, and leadership.

#### Example travel model project: `ActivitySim`

ActivitySim provides a platform for activity-based travel modeling. Like Node.js, ActivitySim has a clearly defined governance structure and development workflow. ActivitySim uses GitHub (see below) to manage the workflow, with a stable version hosted on the master branch, and improvements submitted via pull requests. The governance structure differs from Node.js and similar initiatives because the effort is funded by an association of Municipal Planning Organizations (MPOs). Thus the [governance structure](https://github.com/UDST/activitysim/wiki/Governance) is as follows:

- **Users** uses the modeling tool; users may submit issues to notify developers about bugs or request features.
- **Developers** contribute code or documentation, and act in the "Contributor" role in the figure above.
- **Committers** can accept code from developers, and have signed a CLA. Committers apparently act in all three of the Review, Verification, and Integration steps in the figure. Committers are apparently designated by the Project Management Committee. 
- **Funders** provide funding to support the development of the code and project administration, and may not be involved in the day-to-day of the project.
- **Project Mangagement Committee** (PMC) members serve multiple roles. The PMC is composed of funders initially, and can include developers or committers in the future. As a group, the PMC provides oversight to the whole project. There is a PMC contractor, who acts as the lead organization to carry out the software development and administration, and is likely is the most active component of the Developer and Committer groups.

ActivitySim has a detailed [decision-making](https://github.com/UDST/activitysim/wiki/Governance#decision-making) process, where the most common action (code change) requires no voting, with implicit approval unless a PMC member disagrees. This is also known as "lazy approval" or "lazy consensus", and has been used often in other open source projects (e.g., [Apache](https://forrest.apache.org/guidelines.html)). Another open source project ([`dash.js`](https://github.com/Dash-Industry-Forum/dash.js/wiki/Governance-model)) has written clearly why such implicit consensus is preferable for technical decisions:


> <sub> The vast majority of decisions in an open source project are technical in nature and can therefore be driven by direct contributions to testing, feature management, documentation and code. All such decisions are cheap and easily reversible. We therefore make such decisions by "Lazy Consensus" - a process in which those with merit are trusted to "do the right thing". Non-technical decisions are often harder to reverse and are therefore made through "active consensus" - a process in which anyone can actively build consensus amongst those with merit. </sub>

ActivitySim provides a useful model for VisionEval. Important decisions will include what the composition of the PMC or similar oversight group will be, what decision-making framework the PMC will follow, and how Committers and Developers will be designated. 


## 3.	Open source development   <a name = "opensourcedevelopment"></a>

<!-- Brian Gardner Comment 2017-04-14
We will need to accomplish in the initial phase
1)	 uptake of the AASHTO contract work on RPAT
2)	 Host the prior versions of RPAT
3)	 Release a new major version
4)	 Make at least one maintenance release
5)	 Define a relationship or uptake the ODOT sponsored work

Let's use these tasks to test initial procedures and repository organizations, with input from ODOT on TLUMIP.  -->

Open source development relies on a community of developers to produce, evaluate, and integrate code into a project. There are a number ways that development can be organized in an open source framework, but the most important features are ability to incorporate existing code from other projects, ability to develop features independently, and agreed-upon methods for developers to share their additions with the community of other developers and users.

Incorporating code from other other projects is central to open source development. For example, the Vision California Urban Footprint project is an open-source scenario development and analysis tool for land use planning [(Hosted on GitHub)](https://github.com/CalthorpeAnalytics/urbanfootprint). This project drew from 12 distinct open source projects, including tools for database management, geospatial analysis, and data processing. The open source framework of this project has encouraged multiple users to adopt and modify the tool.  

As development of the VisionEval models has been occurring for several years already, substantial content exists for each of the four models: GreenSTEP, RPAT, RSPM, and EERPAT. The latter three build on the R functions of GreenSTEP, with emphases varying in scale (regional to state-level) and process of interest (land use, greenhouse gas emissions, transportation policies). As a group of free and open source tools, these tools share features and may benefit mutually from improvements in one particular model.

<!-- Ideally, developers contribute to
Reviewing code and maintaining working code base
Testing code under new scenarios
Documenting and updating. 
-->

### Workflow for VisionEval
<!--This section can be written in a similar style to the lest of the paper (less like a draft), but keep as recommendations to give flexibility to the TAC. DF: edited. -->

Contributions to the VisionEval project ideally should follow the typical `git` work flow, using the GitHub web interface as described in detail below. The Pilot Contributor Review Team and Technical Advisory Committee will determine how to proceed; the following presents options for the workflow. In general, the `git` workflow involves creation of a repository (folder of files) of the working version of the code, which is distributed across all the developers. The distributed nature of the repository means that developers can independently make modifications and additions to the code, and then request that this code be incorporated into the main version to be shared with all users. The details of this work flow will be established by the Contributor Review Team, and are outlined here as a starting point.

The initial repository establishment will build off of the RPAT model. This can be done in several methods, one of which is outlined in the [Appendix](http://htmlpreview.github.io/?https://github.com/VisionEval/OSwhitepaper/blob/master/VEwhitepaper_Appendix.html). This procedure, or transfer of repository ownership, would complete the transfer of the RPAT model to the VisionEval project. This would be the version 1.0 release (or other version number), and would become the new master branch. Following the typical GitHub workflow (see [here](https://guides.github.com/introduction/flow/) and below), developers would then add code as necessary to resolve bugs and extend the model with additional features. Contributions from the community would be reviewed and accepted if useful, see below. Documentation of the software tool, essential to grow the community of users, would then be completed, and a new stable version would be released after passing integration tests using tools such as [Travis-CI](https://travis-ci.org/). Keeping the master branch as a stable release is ideal, with continuous development happening on other branches.

This model is illustrated below, showing how releases are made from the master branch, while development occurs on other branches. Image from [nicoespeon.com](http://www.nicoespeon.com/en/2013/08/which-git-workflow-for-my-project/).

![Model workflow for open source development, from nicoespeon.com.](https://raw.githubusercontent.com/VisionEval/OSwhitepaper/master/images/git-flow-branching-model.jpg "Open source development workflow")


### Reviewing contributions from multiple sources

<!--
-	Role of the community of users
-	Gatekeeping versus crowdsource 
-	Merging branches, maintaining stable trunk
-->

Unlike proprietary software projects, open source research projects distinguish between a developer and user community. Contributions from the user community may be rare, typically limited to testing and bug reporting [@Aksulu2010]. Software code review by team members, however, typically follows well-established practice, with careful testing of software products early in the development cycle [@Thongtanunam2016]. The most formal realization of this type of code review involves developers meeting and reviewing printed-out code, line by line. Such review is impractical for large open source projects.

Instead, many open source software projects follow what has been dubbed Modern Code Review (MCR), and is often called a lightweight code review. This type of code review dominates in practice [@Beller2014]. While identifying defects is a core goal of code review, modern code review now also seeks to transfer knowledge, increase awareness, and create of alternative solutions to problems as well [@McIntosh2016]. For scientific research, code review has been proposed to be become an important feature of the peer-review process, to the extent that some authors propose that all source code for statistical analyses must be open during peer review [@shamir2013practices].

GitHub (see below) and other online software repositories allow collaborative code review. The examples illustrated above (Node.js, vegan, and ActivitySim) all feature some way of evaluating code from the community of developers. The key elements of code review are identifying the community members who will carry out the review, having clear standards for what merits useful code to accept, and having a open record of what features are currently desired or being developed.

Identifying the members to carry out the code review is crucial. For projects with clear governance, this should be straightforward, as they will be identified already as Collaborators (Node.js) or  Committers (ActivitySim). For VisionEval, this may be the Contributor Review Team or another set of users they designate.

However the reviewers are designated, there should be clear standards for what code will be accepted. A bare minimum standard is that new features or modules should not break the master; this can be accomplished by automating code testing with tools such as [Travis-CI](https://travis-ci.org/). Beyond this minimum test, ideally there will be a "best practices" guide for developers. For example, the astronomy and astrophysics modeling package AstroPy provides an extensive [guide for developers here](http://docs.astropy.org/en/latest/development/workflow/development_workflow.html). This guide covers stylistic issues of coding as well as details for how to test code and initiate pull requests on GitHub. 

Finally, there will be a list of features which are desired for a project, perhaps with specific features deemed necessary for the next release. AstroPy maintains a formalized list of Proposals for Enhancements on their [wiki](https://github.com/astropy/astropy/wiki/Astropy-Proposals-for-Enhancements), and smaller scale list of features to address for specific releases are maintained on the (issues page](https://github.com/astropy/astropy/milestone/49). Having these clear markers for what is desired will minimize duplicate efforts and motivate developers to contribute.

VisionEval should develop a clear work flow for code review, by following these practices of designating a code review team, standards for code, and list of desired features to solicit contributions.

<!-- 
### Testing new contributions

-	Scenario testing - elasticity  
-	Model data sets
-	Compare output to prior model versions
-->

## 4.	Git and GitHub  <a name = "git"></a>

### Git

Git is a distributed version control system. Git is *distributed* because every user has a complete copy of the repository. Git is a *version control system* in that it tracks the changes to files, allowing useful changes to be incorporated with attribution to the authors. 

At the most basic level, Git manages version control for plain-text files, by tracking changes made at the level of each character in the file. For an individual developer working independently, this feature is already useful, replacing the manual 'version control' commonly done by adding "v2" or the date to a file name. In Git, the most current version of each file is kept, and a snapshot of the differences with previous versions is also kept. Those difference files allow users to examine previous versions of files. 

Other version control software, such as Apache Subversion (SVN), achieve this type of tracking changes for individual files as well. The major difference between Git and other version control systems is the distributed aspect, as opposed to a centralized system. In a centralized version control system like SVN, there is a single master copy of a project. Each developer has to connect to that master copy, make changes to files individually, and then submit it back to the master copy. While one person is working on a file, no other user can edit it. For a small group working on a closed-source project, SVN and similar systems serve very well.

In a decentralized system, anybody can make a copy of the working version of a project ("clone" or "fork" it), work offline or otherwise disconnected from any central server. Multiple users can simultaneously work on projects, since each copy on users' computers is a complete version of the project. If a user has made some changes which they think are of interest to others, they can request that their changes be pulled back to the original. Git suits open-source projects very well, because of this decentralized system, and promotes collaboration among users from different organizations.

Other distributed version control systems exists, such as [Bazaar](http://bazaar.canonical.com/en/) and [Mercurial](https://www.mercurial-scm.org/). These have fewer users, but share many of the same features as Git. A major difference between Git and other systems is the number of users and the online platform for collaborating, GitHub.   

### GitHub

[GitHub](https://github.com) is the Internet platform supporting the use of Git. Git itself does not require the use of GitHub, as it can be used to track file versions on an a single computer. However, in nearly all instances users of Git are collaborating with others via GitHub. GitHub promotes collaboration by facilitating cloning repositories and creating pull requests (see below) to submit project improvements. The other major collaboration tools on GitHub are the presence of a wiki and the issue-tracking tools. Since repositories exist both on the machines of users and on GitHub servers, GitHub can be considered a form of file backup, but does not replace regular backups.  

Issue-tracking can be a powerful way for projects to engage users. The issue-tracking on GitHub provides a means for users to submit bugs or feature easily. Users submitting issues do not necessarily need to be developers with the time and ability to propose new code which solves those issues, simply users interested in improving the project. For example, an open-source data visualization project called Shiny has an active [issue tracking page](https://github.com/rstudio/shiny/issues), with some issues attracting multiple comments from other users, and discussion with the development team. In this case, the project is centralized in governance, with a software development company curating the project with input from users worldwide.

The wiki feature on GitHub is another tool which can both engage users and promote collaboration. Wikis can serve as the complete documentation for a project, at a detailed level. For example, the data visualization project d3 has an extensive and well-curated [wiki](https://github.com/d3/d3/wiki/Gallery), which provides a detailed introduction to the project and links to tutorials, examples, and active user groups.  Like other collaboratively modified web pages, the GitHub wiki tool allows collaborators to make page improvements. However, unlike public wikis such as Wikipedia, collaborators must be identified by the repository owner to be given permission to make edits.

###	Pull requests

Git development is also called pull-based development. The "pull" refers to pulling changes from individual users. On GitHub, the original creator of a repository is the 'owner', and by default the owner is the only user with the ability to merge pull requests from other contributors. This type of collaboration suits open source projects well, as occasional contributions from users can be vetted by the project team, and accepted, rejected, or have further changes proposed.  

This code review process is done on GitHub. While the core team is developing a project, at any time a user can fork a repository, make edits, and then create a pull request. The core team then inspects the changes made by the pull request, and can discuss on GitHub the merits of what the changes would accomplish. In some cases, the core team (composed of the repository owner and collaborators) may ask users to make further changes to their code before accepting the pull requests. On acceptance, the code from the user is merged into project.  

Only a small proportion of projects on GitHub use pull requests, with 14% of project as of 2016 found to have active pull requests [@Gousios2014]. Core team members can make changes by directly committing to the project, and many projects are driven by the core team only. These projects may still be forked and used by others, but are not attracting suggestions for improvement from the user community. 
The majority of pull requests on GitHub projects are for small changes (10 lines of code), attract a small number of comments, and are made by developers who have made a few dozen other pull requests across all GitHub projects. Most pull requests are merged with 4 days of creation [@Gousios2014], demonstrating the rapid pace of development supported by GitHub.

### Documenting changes
 
Documentation of open source projects occurs at both the small and large scale. At the small scale, every change made by commits to a project or via pull requests need to be documented. Every commit on Git requires a short message to document the specific change, and pull requests are documented by the Pull Requests tab on a GitHub page. At a larger scale, developers need to provide documentation about how to use the tools, which is done in both a brief README file and ideally in greater detail on the GitHub wiki. For some projects, a separate PDF file may exist as the project documentation, but such a static file may not serve the needs of an actively-developing project. For active projects, a wiki should serve as the complete documentation.

Major updates to projects may be documented by creating a release, which has a version number and brief notes to document the significant changes. Releases provide a way to mark major changes to the software tools. Since users are not downloading executable files in the traditional method of releasing software, the GitHub releases are simply milestones marking points that the core team has decided are significant changes, and can provide static snapshots of the project at that time. An example of an R package of analysis tools used by biologists [here](https://github.com/vegandevs/vegan/releases) shows how the source code for specific releases is bundled into archive files, with extensive documentation. 


### Communicating with the user community

Successful projects have a community of users who employ and improve the tools of the project. Users can become engaged in the project by contributing suggestions via the issue-tracking tool on GitHub, or directly contributing project improvements with pull requests. However, one common method of engaging users not supported by GitHub is a forum for users to ask general questions and share knowledge. <!-- The following sentence is not clear - check edits made -->
Such forums include distribution platforms such as the [Open Source Application Development Portal](https://www.itsforge.net/index.php/community/discussion-forum) of the Federal Highway Administration, or individual project web pages, such as the [UrbanSim](http://discussion.urbansim.com/) project for planning and analysis of urban development. User forums of a sort also exist outside of official project web pages, for example on the highly active Stack Overflow site. This site which allows developers to ask and answer questions about specific problems with a tool, or about issues more general than one tool. A forum can be developed for a GitHub Pages site, which is a way to host a front-end website for a GitHub project.

<!--Are these valid assumptions? Will you have less technical users that are not familiar with GitHub? DF: Use of Issues should be relatively easy to understand. -->

For projects such as VisionEval which will likely have a small number of specialized users, a discussion forum may not be the most beneficial tool. Instead, using Issues on GitHub likely will present the best way for users to discuss specific technical topics about VisionEval tools. As users of VisionEval tools will be technically sophisticated enough to know about and use GitHub, keeping the online discussion on the GitHub pages (namely, the Issue tracker) will be the most convenient way to host discussions. 

In addition to online discussions, periodic announcements by email can be useful. Such announcements may be on at regular periods, or following releases of major updates or new modules. Maintaining a list of interested users would require some investment of effort for the centralized governing organization. Large open source projects with many active users do not typically have email announcements, but for VisionEval such announcements could be useful for engaging the community of users who are not developers. 

<!-- general SO example: https://gis.stackexchange.com/questions/68349/are-there-open-source-solutions-for-travel-demand-modelling -->
<!-- Disqus forum for GitHub pages: http://klcodanr.github.io/Jekyll-Disqus-Forum/ -->

## 5.	Recommendations  <a name = "summary"></a>

As an ongoing open source development effort, VisionEval has already implemented key best practices, namely developing the software in an open, public fashion with documentation of the contributions being made. Making VisionEval a vibrant community of users and developers will require a few additional steps. These include:

- Agree on a license which meets the needs of the VisionEval charter. The VisionEval team should consider as permissive a license as possible, so that the public may benefit from these strategic planning tools. Patent protection and the need to have releases from individual developers (CLAs) should be considered. 

- Develop a governance structure which establishes the roles and responsibilities of users, developers, and collaborators/committers, as well as an oversight body composed of funders. Following the ActivitySim structure would appear to be a useful way forward.

- Develop a code review process which is clear and fair, to maximize contributions from the community. This will be likely done on GitHub, using a pull request model to merge new features into the development branch, with periodic merges into the master branch when warranted to release a new version. 

- Clearly document the software tools, to grow the community of users and developers. Guidance for developers should be a priority, including conventions about how to comment code and how new functions will interact with existing functions. A project wiki on GitHub (or one for each of the VisionEval models) would be recommended. Mailing lists for users and developers may not be necessary at first, as the issues page on GitHub can serve most of the needs for communicating. A project webpage (https://pages.github.com/) may be useful, to provide a simple interface for non-developer users. 

- Release stable versions periodically, maintaining active development branches for new features. Releases can be announced by email if an email list is developed, or simply announced on the GitHub page.

Taking these steps will help grow the community of users and developers to collaboratively develop the VisionEval strategic planning tools. 

# References
