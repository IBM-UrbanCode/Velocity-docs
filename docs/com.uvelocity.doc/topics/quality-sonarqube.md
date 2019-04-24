# Integrating with SonarQube

Accessing SonarQube data with the SonarQube integrations.

The SonarQube integration use SonarQube web hooks and to request data that it uses to populate a data set. Like other quality data integrations, this one operates in the reporting-consumer service.

The integration uses REST endpoints and quality data handlers to perform the following steps:

1.  Receive a web-hook payload from SonarQube.
2.  Request additional SonarQube issues.
3.  Make three successive calls to the RE API `uploadQualityData` endpoint. The calls validate and store data documents, one for each issue category: bugs, code smells, security vulnerabilities.

1.   Create a SonarQube instance with properly configured certificates. 
2.   Create a web hook in SonarQube, **Administration** \> **Webhooks**, that defines a URL as such: `http://<UCV-Reporting-Consumer\>/pluginEndpoint/<Integration-ID\>/sonarqube/callback`.

When you run a SonarQube job against the instance, it performs the specified workflow.

**Parent topic:** [Integrating quality data](../topics/c_node_qualityData.md)

