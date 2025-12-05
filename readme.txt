New feature in ec
few more changes


YANG:

This repository contains a collection of YANG modules:

IETF standards-track YANG modules
IEEE experimental YANG modules
ETSI standard YANG modules
MEF standard YANG modules
Broadband Forum standard YANG modules
Vendor-specific YANG modules
Contribution Procedures
Direct Contributions
This is the preferred method of contribution. With this approach you pick where your models will reside in the directory hierarchy, and manage the files mainly in your own fork of the main repository, submitting a pull request when you wish to make public updated models. All push requests must be reviewed by at least one of the repository's Committers, so when pushing a PR, please assign it to one of the committers.

You can find a tutorial here for how to do push requests. Note that there are at least two different approaches to how to do Pull Requests: using a shell/commandline or using the web interface, so if you do not find what you need below, look elsewhere or ask the committers for pointers.

https://yangsu.github.io/pull-request-tutorial/

By convention, there should also be a check.sh script provided by the contributors, which should be referenced from the complete_check.yml file for CI builds. Multiple examples are already in place to copy and modify as required.

Contributions Via Submodules
Standards bodies or vendors may also provide models to the main repository via a git submodule. Examples of this can be see under standard directory, with the BBF and MEF submodules. By convention, if a submodule is used, there should also be an equivalent check.sh provided by the contributors, which should be referenced from the complete_check.yml file for CI builds. An example of this may be found in the BBF's submodule, and a sample invocation here.

Direct contributions to the top level of the repository are not encouraged; instead each "organization" should create a top-level folder as described above.

A summary of the suggested process is:
Create a fork of https://github.com/YangModels/yang
Enable Github Actions on your fork in the Actions tab
Add your source git repository as a submodule to your fork:
Clone your fork
cd into vendor or standards directory (depending on the source of your models)
git submodule add https://github.com/<owner>/<repository>.git <name>
Add appropriate entry to the complete_check.yml file to check your models.
Note: this requires a call to a check.sh script provided by the contributors, which should be referenced from the complete_check.yml file for CI builds. Multiple examples are already in place to copy and modify as required, but in general, one is present at the top-most level of each major submodule area.
Commit changes to your fork
Test the Github Actions CI run of your fork as well as test it by running the testall.sh script from the top level directory.
After you've verified that the submodule addition and module checking is working ok, submit a PR to the main repository. This will take the latest commit from your repository and make it available as a submodule.

Subsequently, when an updated set of models needs to be released, fork, clone, update submodule, commit and submit PR, also ensuring that Github Actions are again enabled on your fork to allow pre-pull request checks.

All Pull Requests must be reviewed and as such one of the repository's Committers must review the request prior to actually committing the request. Changes may be suggested during this process, so patience is requested during this process.