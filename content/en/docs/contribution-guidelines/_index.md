
---
type: docs
title: "Contribution Guideline"
linkTitle: "Contribution Guideline"
description: "Guidelines for contributing to Dubbo"
weight: 90
---


Dubbo is released under the non-restrictive Apache 2.0 license, and follows a very standard Github development process, using Github tracker for issues and merging pull requests into master. If you want to contribute even something trivial please do not hesitate, but follow the guidelines below.

### Contact

#### Mailing list

The mailing list is the recommended way for discussing almost anything that related to Dubbo. Please refer to this [guide](https://github.com/apache/dubbo/wiki/Mailing-list-subscription-guide) for detailed documentation on how to subscribe.

- [dev@dubbo.apache.org](mailto:dev-subscribe@dubbo.apache.org): the develop mailing list, you can ask question here if you have encountered any problem when using or developing Dubbo.
- [commits@dubbo.apache.org](mailto:commits-subscribe@dubbo.apache.org): all the commits will be sent to this mailing list. You can subscribe to it if you are interested in Dubbo's development.
- [notification@dubbo.apache.org](mailto:notification-subscribe@dubbo.apache.org): all the Github [issue](https://github.com/apache/dubbo/issues) updates and [pull request](https://github.com/apache/dubbo/pulls) updates will be sent to this mailing list.

### Reporting issue

Please follow the [template](https://github.com/apache/dubbo/issues/new?template=dubbo-issue-report-template.md) for reporting any issues.

### Code Conventions
Our code style is almost in line with the standard java conventions (Popular IDE's default setting satisfy this), with the following additional restricts:  
* If there are more than 120 characters in current line, start a new line.

* Make sure all new .java files to have a simple Javadoc class comment with at least a @date tag identifying birth, and preferably at least a paragraph on what the class is for.

* Add the ASF license header comment to all new .java files (copy from existing files in the project)

* Make sure no @author tag added to the file you contribute since @author tag is not used at Apache, other ways such as cvs will record all your contributions fairly.

* Add some Javadocs and, if you change the namespace, some XSD doc elements.

* A few unit tests should be added for a new feature or an important bugfix.

* If no-one else is using your branch, please rebase it against the current master (or other target branch in the main project).

* When writing a commit message please follow these conventions, if you are fixing an existing issue please add Fixes #XXX at the end of the commit message (where XXX is the issue number).

### Contribution flow

This is a rough outline of what a contributor's workflow looks like:

* Fork the current repository
* Create a topic branch from where to base the contribution. This is usually master.
* Make commits of logical units.
* Make sure commit messages are in the proper format (see below).
* Push changes in a topic branch to your forked repository.
* Follow the checklist in the [pull request template](https://github.com/apache/dubbo/blob/master/PULL_REQUEST_TEMPLATE.md)
* Before you sending out the pull request, please sync your forked repository with remote repository, this will make your pull request simple and clear. See guide below:

    ```bash
    git remote add upstream git@github.com:apache/dubbo.git
    git fetch upstream
    git rebase upstream/master
    git checkout -b your_awesome_patch 
    ... add some work
    git push origin your_awesome_patch
    ```
* Submit a pull request to apache/dubbo and wait for the reply.
* All pull requests are automatically tested on [GitHub Actions](https://github.com/apache/dubbo/actions) for AMD64 CPU architecture. Please check that all builds are successful! Additionally there are nightly tests set up at [TravisCI](https://travis-ci.com/github/apache/dubbo) to prevent any regressions on ARM64 CPU architecture.

Thanks for contributing!

### Code style

We provide a template file [dubbo_codestyle_for_idea.xml](https://github.com/apache/dubbo/tree/master/codestyle/dubbo_codestyle_for_idea.xml) for IntelliJ idea, you can import it to you IDE. 
If you use Eclipse you can config manually by referencing the same file.

{{% alert title="Notice" color="primary" %}}
It is very important to set the dubbo_codestyle_for_idea.xml, otherwise you will fail to pass the Travis CI. Steps to set the code style are as below:

1. Enter `Editor > Code Style`
2. To manage a code style scheme, in the Code Style page, select the desired scheme from the drop-down list, and click "manage profiles"
From the drop-down list, select `Import Scheme`, then select this option `IntelliJ IDEA code style XML` to import scheme
3. In the Scheme field, type the name of the new scheme and press ⏎ to save the changes.
{{% /alert %}}





