# Integrating JUnit data

Incorporate JUnit quality data into workflows, reports, and pipelines.

## Integrating JUnit data

The JUnit integration parses JUnit XML files and forwards the data to the UrbanCode™ Velocity application API.

Quality data integrations expose modules that follow simple interfaces. This is done by exposing implementations in the index.js file, as shown in this example:

`POST https://Velocity\_URL/reporting-consumer/qualityData`

The multipart-form data is shown in the following example:

```
payload: <Payload JSON Object String\>
testArtifact: <JUnit XML File\>
```

## Sample request

The following code fragment provides a sample Curl post request:

```
curl --request POST \
  --url https://<Velocity Base URL>/reporting-consumer/qualityData \
  --form 'payload={
  "tenant_id": "<TOKEN>",
  "application": {
    "name": "My Application"
  },
  "record": {
    "pluginType": "junitXML",
    "dataFormat": "junitXML"
  }
}
' \
  --form testArtifact=@test-result/junit.xml
```

## Detailed JUnit request format

The following code fragment provides a sample JUnit request:

```
{
  "tenant_id": "<TOKEN\>",
  "metricName": "Unit Tests for My Application", // optional label
  "application": {
    "name": "My Application"
  },
  "record": {
    "recordName": "Unit Tests for My Application on 10/12/2022", // optional label
    "executionDate": 1547983466015, // optional unix epoch
    "pluginType": "junitXML",
    "dataFormat": "junitXML"
  },
  "options": {
      "combineTestSuites": true // false by default
  }
}
```

**Parent topic:** [Integrating quality data](../topics/c_node_qualityData.md)

