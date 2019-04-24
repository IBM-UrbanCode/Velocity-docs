# Integrating Visual Studio data

Accessing Visual Studio quality data.

## Integrating Visual Studio data

This integration provides Visual Studio formatted unit tests and code coverage data to UrbanCode Velocity.

## Unit test data

Supported formats are `UNIT_TEST` and `UNIT_TEST_DURATION`.

|Plug-in Type|Data Format|Description|
|------------|-----------|-----------|
|msTest|vsTestTRX|VSTest .trx files|
|msTest|vsTestXML|VSTest .xml files|
|msTest|msTestTRX|MSTest .trx files|
|msTest|msTestXML|MSTest .xml files|

## Code coverage data

Supported formats are `COVERAGE_LINES` and `COVERAGE_FUNCTIONS`.

**Note:** Note that branch coverage information is not provided.

|Plug-in Type|Data Format|Description|
|------------|-----------|-----------|
|vsCoverage|vsTestCoverageXML|VSTest .xml files|
|msCoverage|msTestCoverageXML|MSTest .xml files|

**Parent topic:** [Integrating quality data](../topics/c_node_qualityData.md)

