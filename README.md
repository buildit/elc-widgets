# elc-widgets

A custom ServiceNow application creating Service Portal widgets that highlight topics in a browser,
with a look and feel very close to the `relevant_for_you` widget.

# Installation

The course [Build the Needit Application](https://developer.servicenow.com/dev.do#!/learn/courses/rome/app_store_learnv2_buildneedit_rome_build_the_needit_application/app_store_learnv2_buildneedit_rome_create_the_needit_application_and_application_files/app_store_learnv2_buildneedit_rome_importing_an_application_from_source_control)) from https://developer.servicenow.com/ shows how to import an application from a Git repository. While that is not the normal way many work with ServiceNow, it was one of the first things I learned and I was already very well acquainted
with Git but not familiar with update sets.

In addition, the custom application has been published for the relevant company, and should be able to be installed throughout the company's instances.

# Development Methods

The main capabilities used to develop these widgets was Chrome's Developer Tools and the Widget Editor within Service Now.

## Debugging AngularJS with Chrome Developer Tools

After loading the home page, follow the following steps to see what are a widgets options and data:
* Press F12 to enter Developer Tools
* Navigate to the JavaScript console
* Enter: `angular.reloadWithDebugInfo()`.  The entire page will reload.
* Use the mouse to hover over an element likely within the widget you want to debug.
* Right click and select "Inspect" - this brings you back to the Developer Tools.
* Within the elements hierarchy, move to different elements until you are at one with an "ng-scope" attribute - this is an AngularJS component, and likely a Service Portal widget.
* Move back to the JavaScript console, and enter `angular.element($0).scope()`.  This will show you want "options" the widget was created with, and what "data" it has from the server side script.

## Working with the Widget Editor

* Take the course [Service Portal](https://developer.servicenow.com/dev.do#!/learn/courses/rome/app_store_learnv2_serviceportal_rome_service_portal) from the developer site to learn more about this.
* The course [Scripting in ServiceNow](https://developer.servicenow.com/dev.do#!/learn/courses/rome/app_store_learnv2_scripting_rome_scripting_in_servicenow) is also useful and goes in more depth on debugging, but some of these options are not available for the Service Catalog.

## Embedded Widgets

* One thing needed is to be familiar with how to embed widgets in other widgets.  This is discussed at the [Embedded widgets](https://docs.servicenow.com/bundle/rome-servicenow-platform/page/build/service-portal/concept/c_NestedWidgets.html) documentation page.

## Other Resources

Always keep the AngularJS developer guide and reference nearby:
* https://docs.angularjs.org/guide
* https://docs.angularjs.org/api

Remember that AngularJS is very different now from Angular.  Specifically because AngularJS can and often is used directly from JavaScript, whereas Angular is more often written in TypeScript.
