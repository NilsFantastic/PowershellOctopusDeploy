# Deploy local folder with octopus

Example usage - only required parameter is version
- run powershell in your project folder
- .\deploy-local-folder-with-octopus.ps1 1.2.1234

**Parameters**
The parameters are unnamed and required to be used in correct order. the order is as follows
- [string] $versionNumber 
    - _the version number for the octopus release_
- (Optional)[string]$projectName
    -  _The name of the project in octopus. Put inside quotation marks like: "Project Name"_
- (Optional)[string]$apiKey
    -  _Generate this from your profile page in octopus deploy. The key should look like: API-XXXXXXXXXXXXXXXXXXXXXXXXXX_
- (Optional) [string]$packageName
    - _This can be named however you like. The name will be shown when you use the "Create Release" button in Octopus Deploy and get to choose which package to deploy_
- [string]$nugetPackageFolder
    - Defaults to: "\." This is the folder from which the nupkg will be created. It can be set to a subdirectory in case your project for example has a "www"/"dist/bin" folder which holds the actual application.
- [string]$deployToEnvironment
    - This is the name of the environment in Octopus Deploy you wish to target. For example: TEST, PRODUCTION

**Example with all parameters set**

.\deploy-local-folder-with-octopus.ps1 1.2.1234 "Hello World App" API-XXXXXXXXXXXXXXXXXXXXXXXXXX hello_world_app .\bin TEST