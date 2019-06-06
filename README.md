<!-- SHIELDS -->


<!-- PROJECT LOGO -->
<br />

<p align="center">
    <a href="https://github.com/douglascayers-org/sfdx-mass-action-scheduler/">
        <img src="images/mas-logo.png" alt="Mass Action Scheduler Logo" />
    </a>
    <br />
    Declaratively schedule process automation from reports and list views!
    <br />
    <a href="https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Examples">View Demo</a>
    ·
    <a href="https://github.com/douglascayers-org/sfdx-mass-action-scheduler/issues">Report Bug</a>
    ·
    <a href="https://github.com/douglascayers-org/sfdx-mass-action-scheduler/issues">Request Feature</a>
</p>

## About the Project

Put the power of [Batch Apex](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_batch.htm) within reach of [declarative configuration](https://help.salesforce.com/articleView?id=extend_click_intro.htm&type=5). Declaratively schedule Process Builder, Flows, Quick Actions, Email Alerts, Workflow Rules, or Apex to process records from Reports, List Views, SOQL, or Apex.

Inspired by Marie Chandra's idea [Ability to Schedule when Process Builder Triggers](https://success.salesforce.com/ideaView?id=08730000000DjEmAAK).

Inspired by Narender Singh's idea [Ability to schedule flows, workflows and processes in process builder](https://success.salesforce.com/ideaView?id=0873A000000EA71QAG).

No more waiting for records to be updated or creating clever workarounds to cause records to be updated to cause these actions to fire.

## Features

**Declarative** - no code necessary, never write Batch Apex again for queries that can be expressed in a report or list view and actions that can be expressed with a declarative alternative.

**On Platform** - everything happens in Salesforce so no exporting or uploading data necessary.

**Timely** - run actions manually or schedule hourly, daily, weekly, or any time in between.

## Documentation and Discussion

* For discussion and feedback [post in the community group](https://success.salesforce.com/_ui/core/chatter/groups/GroupProfilePage?g=0F93A000000LhvN) or raise well defined issues and ideas via the [issue tracker](https://github.com/douglascayers/sfdx-mass-action-scheduler/issues).
* Read the [wiki page](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki) for further documentation on Mass Action Scheduler.
* Read the [FAQ page](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Frequently-Asked-Questions) to help troubleshoot technical issues.

## Pre-Requisites

There are a few items you need to setup before installing and using this app.

1. You will need to [Enable Lightning Experience](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Pre-Requisites-Instructions#1-enable-lightning-experience) because we are using Lightning Components.
2. You will need to [Enable My Domain](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Pre-Requisites-Instructions#2-enable-my-domain) because we are using Lightning Components.
3. You will need to [Allow IFraming of Visualforce Pages with Clickjack Protection](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Pre-Requisites-Instructions#3-allow-iframing-of-visualforce-pages-with-clickjack-protection) because we iframe pages in Lightning Components.

Please see the [instructions in the wiki](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Pre-Requisites-Instructions) for screen shots and step-by-steps.

## Packaged Release History

### Support

Mass Action Scheduler is a free and independently developed passion project of mine.

If your business has found value in my open source projects, please consider showing your support:
  * :star: Star this project on GitHub
  * Contribute a :coffee: or :hamburger: via my [virtual tip jar on PayPal](https://www.paypal.me/douglascayers/)

[Thank you](https://douglascayers.com/thanks-for-your-support/)! :heart:

### Release 2.2 (current)

_Due to Lightning Experience web page caching, please log out and log back in after installing the package for UI changes to appear._

* Install Package
    * Browser Links ([Production](https://login.salesforce.com/packaging/installPackage.apexp?p0=04tf4000004MdAC)) ([Sandbox](https://test.salesforce.com/packaging/installPackage.apexp?p0=04tf4000004MdAC))
    * Salesforce CLI (`sfdx force:package:install --package 04tf4000004MdAC --wait 10`)
* [Release Notes](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/wiki/Release-Notes)
* [Closed Issues](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/milestone/7?closed=1)
* [Archived Releases](https://github.com/douglascayers-org/sfdx-mass-action-scheduler/milestones?state=closed)

---

### Installing the Source Code (Developers)

This repository is organized using [Salesforce DX](https://trailhead.salesforce.com/en/trails/sfdx_get_started).
You may install the source code from GitHub and make any desired adjustments.
You are responsible for ensuring unit tests meet your org's validation rules and other requirements.

First, clone the repository.

```
git clone https://github.com/douglascayers-org/sfdx-mass-action-scheduler.git
```

Change directory into the project folder.

```
cd sfdx-mass-action-scheduler
```

Create a new scratch org.

```
sfdx force:org:create -a mas -s -f config/project-scratch-def.json
```

Push the source metadata into your scratch org.

```
sfdx force:source:push
```

Assign the permission set to your user. 

```
sfdx force:user:permset:assign -n Mass_Action_Admin
```

Create a test account, only required for the report tests.

```
sfdx force:data:record:create --sobjecttype Account --values "Name='dca_mass_action: MA Test Account'"
``` 

Run unit tests.

```
sfdx force:apex:test:run --codecoverage --resultformat human --wait 10
```

Open the scratch org and enjoy!

```
sfdx force:org:open --path //lightning/o/Mass_Action_Configuration__c/list
```


## Credits

[Doug Ayers](https://douglascayers.com) develops and maintains the project.

[Appiphony](http://www.lightningstrike.io) for developing the Strike Wizard component based on Lightning Design System [Path blueprint](https://www.lightningdesignsystem.com/components/path/).

[Salesforce Foundation](https://github.com/SalesforceFoundation/CampaignTools) for developing tools for querying Salesforce Reports API in Apex.

[Shinichi Tomita](https://twitter.com/stomita) for developing [jsforce](https://jsforce.github.io/) and [soql-parse](https://github.com/stomita/soql-parse) libraries for easy use of Salesforce REST APIs in JavaScript.

[jQuery](https://jquery.com/) for developing jQuery library.

[Aaron Hardy](https://twitter.com/aaronius) for developing [Penpal](https://github.com/Aaronius/penpal), a promise-based library for securely communicating with iframes via postMessage.


## License

The source code is licensed under the [BSD 3-Clause License](LICENSE)
