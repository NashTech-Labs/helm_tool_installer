# helm_tool_installer
 How to install the Helm CLI. Helm can be installed either from source, or from pre-built binary releases. From The Helm Project. The Helm project provides two ways to fetch and install Helm. These are the official methods to get Helm releases


## Parameters:
The pipeline requires the following parameters to be defined:


| Name  | Displayname | type | Default | Values | Optional/Required | Comments |
| ------------- | ------------- | :-------------: | :-------------: | ------------- | :-------------: | ------------- |
| helmVersionToInstall | Helm Version Spec | string | latest | | Required | Specifies the version of Helm to install. Acceptable values include any semantic version string, like 2.14.1 |

--------------------------------------------------------------------------------------------------------------------------------------------------

These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/helm_tool_installer
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: helm_tool_installer.yml
    parameters:
      helmVersionToInstall: '${{parameters.helmVersionToInstall}'
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.
