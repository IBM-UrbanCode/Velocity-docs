# Integrating code coverage quality data

Integrate code coverage data into your workflows, pipelines, and reports.

## Integrating code coverage data

This integration provides several types of code coverage data to UrbanCode™ Velocity. These following formats are currently supported:

-   Cobertura
-   Icov \(Linux\)
-   generic code coverage

These quality data integrations expose modules that follow simple interfaces. This is done by exposing implementation in the index.js file as seen in this example:

`POST https://Velocity\_URL/reporting-consumer/qualityData`

The multipart-form data is shown in the following example:

```
payload: <Payload JSON Object String>
testArtifact: <cobertura/etc XML File>
```

## Sample Cobertura request

The following code fragment provides a sample Curl post request:

```
curl --request POST \
  --url https://<Velocity Base URL>/reporting-consumer/qualityData \
  --form 'payload={
  "tenant_id": "<TENANT ID>",
  "application": {
    "name": "My Application"
  },
  "record": {
    "pluginType": "coverageData",
    "dataFormat": "cobertura"
  }
}
' \
  --form testArtifact=@test-result/junit.xml
```

## Detailed Cobertura format

The following code fragment provides a sample Cobertura request:

```
{
  "tenant_id": "<TENANT ID>",
  "metricName": "Unit Test Coverage for My Application", // optional label
  "application": {
    "name": "My Application"
  },
  "record": {
    "recordName": "Unit Test Coverage for My Application on 10/12/2022", // optional label
    "executionDate": 1547983466015, // optional unix epoch
    "pluginType": "coverageData",
    "dataFormat": "cobertura"
  }
}
```

## Code coverage data API

If your coverage format is not provided, you can simulate this integration's top-level output by using a series of template requests using the `normalizedQuality` category:

-   `COVERAGE_LINES`
-   `COVERAGE_FUNCTIONS`
-   `COVERAGE_BRANCHES`

You can provide covered and found values on `record.value` requests, as shown in the following Curl example:

```
curl --request POST \
  --url https://<Velocity Base URL>/reporting-consumer/qualityData \
  --form 'payload={
    "tenant_id": "<TENANT ID>",
    "environment": "fooEnvironment",
    "metricName": "Code Coverage for Functional Tests",
    "pullRequestId": "123123",
    "commitId": "123213",
    "integrationId": "12345",
    "application": {
      "name": "ucv:application_api"
    },
    "build": {
      "buildId": "1234",
      "jobExternalId": "1234",
      "url": "http://url.com"
    },
    "record": {
      "pluginType": "normalizedQuality",
      "category": "COVERAGE_LINES",
      "value": {
        "numerator": 330,
        "denominator": 1023
      },
      "valueType": "percent",
      "executionDate": 1547983466015,
      "dataFormat": "cobertura"
    }
  }'
```

**Parent topic:** [Integrating quality data](../topics/c_node_qualityData.md)

