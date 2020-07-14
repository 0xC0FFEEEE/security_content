# Splunk Security Content
![security-content](docs/static/logo.png)
=====

| branch | build status |
| ---    | ---          |
| develop| [![develop status](https://circleci.com/gh/splunk/security-content/tree/develop.svg?style=svg&circle-token=67ad1fa7779c57d7e5bcfc42bd617baf607ec269)](https://circleci.com/gh/splunk/security-content/tree/develop)|
| master | [![master status](https://circleci.com/gh/splunk/security-content/tree/master.svg?style=svg&circle-token=67ad1fa7779c57d7e5bcfc42bd617baf607ec269)](https://circleci.com/gh/splunk/security-content/tree/master)|

Welcome to the Splunk Security Content

This project gives you access to our repository of Analytic Stories that are security guides which provide background on TTPs, mapped to the MITRE framework, the Lockheed Martin Kill Chain, and CIS controls. They include Splunk searches, machine-learning algorithms, and Splunk Phantom playbooks (where available)—all designed to work together to detect, investigate, and respond to threats.

# Usage🛡
The Splunk Security Content can be used via:

#### [Splunk App](https://github.com/splunk/security-content/releases) 
Grab the latest release of DA-ESS-ContentUpdate and install it on a Splunk Enterprise instance. Alternatively you can download it from [splunkbase](https://splunkbase.splunk.com/app/3449/), it is currently a Splunk Supported App.

#### [API](https://docs.splunkresearch.com/?version=latest)
```
curl -s https://content.splunkresearch.com | jq
{
  "hello": "welcome to Splunks Research security content api"
}
```

#### [GitHub Workflow](https://github.com/splunk/security-content/wiki/Installation-and-Usage)
Create your customized version of Security Content by forking this project and following this [guide](https://github.com/splunk/security-content/wiki/Installation-and-Usage#github-workflow).

# Customize to your Environment 🏗
Customize you content to change how [often detections run](https://github.com/splunk/security-content/wiki/Customize-to-Your-Environment#customizing-scheduling-and-alert-actions-with-deployments), or what the right source type for [sysmon](https://github.com/splunk/security-content/wiki/Customize-to-Your-Environment#customizing-source-types-with-macros) in your environment is please follow this [guide](https://github.com/splunk/security-content/wiki/Customize-to-Your-Environment).  

# Execute an Analytic Story 🏃‍♀️
Download and install the latest version of [Splunk Analytic Story Execution]
(https://github.com/splunk/analytic_story_execution/releases). This Splunk application will help the user do the following:

1. Execute an analytic story in an adhoc mode and view the results.
2. Schedule all the detection searches in an analytic story.
3. Update security-content via an API

# Writing Content 📓
Please see the Developing Content [guide](https://github.com/splunk/security-content/wiki/Developing-Content) for instructions.

# Content Parts 🧩

* [detections/](detections/): Contains all 209 detection searches to-date and growing.
* [stories/](stories/): All Analytic Stories that are group detections or also known as Use Cases
* [deployments/](deployments/): Configuration for the schedule and alert action for all content
* [responses/](responses/): Incident Response Playbooks/Workflow for responding to a specific Use Case or Threat.
* [response_tasks/](response_tasks/): Individual steps in responses that help the user investigate via a Splunk search, automate via a phantom playbook, and visualize via dashboards threats.
* [baselines/](baselines/): Searches that must be executed before a detection runs. It is specifically useful for collecting data on a system before running your detection on the collected data.
* [dashboards/](dashboards/): JSON definitions of Mission Control dashboards, to be used as a response task. Currently not used.
* [macros/](macros/): Implements Splunk’s search macros, shortcuts to commonly used search patterns like sysmon source type. More on how macros are used to customize content below.
* [lookups/](lookups/): Implements Splunk’s lookup, usually to provide a list of static values like commonly used ransomware extensions.

#### Supporting Parts
* [package/](package/): Splunk content app-source files, including lookups, binaries, and default config files
* [bin/](bin/): All binaries required to produce and test content

# Contribution 🥰
We welcome feedback and contributions from the community! Please see our [contributing to the project](https://github.com/splunk/security-content/wiki/Contributing-to-the-Project) for more information on how to get involved.

## Support 💪
Please use the [GitHub Issue Tracker](https://github.com/splunk/security-content/issues) to submit bugs or request features.

If you have questions or need support, you can:

* Post a question to [Splunk Answers](http://answers.splunk.com)
* Join the [#security-research](https://splunk-usergroups.slack.com/messages/C1RH09ERM/) room in the [Splunk Slack channel](http://splunk-usergroups.slack.com)
* If you are a Splunk Enterprise customer with a valid support entitlement contract and have a Splunk-related question, you can also open a support case on the https://www.splunk.com/ support portal
