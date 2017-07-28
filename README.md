Flow SoapUI Plugin
-------------------------------

*Tested to work  on SoapUI OS 5.2.0*

[![Build Status](https://travis-ci.org/O5ten/flow-soapui-plugin.svg?branch=master)](https://travis-ci.org/O5ten/flow-soapui-plugin)

Some services are dependent on inherently unstable services. This plugin is developed to resolve that particular problem and functionally test even unstable endpoints. 
It is a plugin that gives the power to the user and the possibility to have unstable test-steps. Primarily it allows them to fail and pass through a repetition procedure. 

Install
-------------------------------

```bash
 mvn clean install 
```

copy the ``` target/flow-soapui-plugin-1.0.0.jar ``` and put it in ``` ${USER_HOME}/.soapuios/plugins```

or run with the deploy-profile to let maven move it to your home-folder for you

```bash
 mvn clean install -Pdeploy
```

Unsigned Plugin
-------------------------------

In SoapUI OS 5.2.1 a signing procedure was introduced to hash out what product the plugin is included with.
This plugin is not signed and can thereby only be used with SoapUI OS 5.2.0 and earlier. 

If you want to test it on 5.2.1+ you will have to build
hschotts Jailbreak Plugin and put it in ``` ${SOAPUI_HOME}/jre/lib/ext ```

```
 https://github.com/hschott/soapui-pluginloader-jailbreak
```

Usage
-------------------------------

- Add the repeat teststep to your testcase
- select a target teststep which from where the testcase will be iterated from
- select a maximum number of attempts
- Run unstable testcase

The test will be rerun from that point until all teststeps are successful or maximum number of attempts are reached

Examples
-------------------------------

Since it's difficult to use anything without having an example to consult there is a sample project included that shows the intended use-cases. 

![Picture of the teststep][1]

You can find it[here][2]
 
Future Work/Feature Requests
-------------------------------

- Make it possible to use conditionals or xpath, json-query to decide whether to continue iterating or not. Like Conditional Goto. 
- Mock-Service-control test-steps, today you have to script to do that. 
- SSH Test-Steps 

[1]: https://github.com/O5ten/flow-soapui-plugin/blob/master/repeat-test-step.jpg
[2]: https://github.com/O5ten/flow-soapui-plugin/blob/master/Unstable-Endpoint-SoapUI-project.xml