# Azure API Management Insights

This repository contains an Azure Workbook for monitoring and analyzing Azure API Management (APIM) resources.

## Workbook Features

The `azure-api-management-insights.json` workbook provides comprehensive monitoring capabilities for Azure API Management services including:

### Parameters
- **Log Analytics Workspace Selection**: Choose the Log Analytics workspace where your APIM diagnostic logs are stored
- **API Management Service Selection**: Pick the specific APIM service to monitor (optional - leave blank to monitor all APIM services sending logs to the workspace)
- **Time Range Selection**: Choose the time window for analysis (defaults to last hour)

### Visualizations

#### Request Overview
- **API Requests Over Time**: Time-series chart showing request volume
- **Request Summary**: Tile view with total requests, success rates, and error rates

#### Performance Metrics
- **Response Time Percentiles**: Chart showing average, 50th, 95th, and 99th percentile response times
- **Backend Response Time**: Analysis of backend service performance

#### Error Analysis
- **Error Rates by Response Code**: Time-series breakdown of errors by HTTP status code
- **Top APIs by Error Count**: Table showing which APIs generate the most errors

#### Capacity and Performance
- **API Management Capacity Utilization**: Monitor APIM service capacity usage
- **Top APIs by Request Volume**: Pie chart showing request distribution across APIs

## Usage

1. Import the workbook JSON file into Azure Monitor Workbooks
2. Select your Log Analytics workspace where APIM diagnostic logs are stored
3. Optionally select a specific APIM service (leave blank to monitor all services)
4. Choose your desired time range (defaults to last hour)
5. View comprehensive metrics and logs for your APIM service(s)

## Technical Implementation

The workbook uses KQL queries targeting:
- `ApiManagementGatewayLogs` - For request, response, and error data (resource-specific logs)
- `AzureDiagnostics` - For legacy diagnostic logs with Category == "GatewayLogs"
- `AzureMetrics` - For capacity and performance metrics

The workbook automatically handles both resource-specific log tables and legacy Azure Diagnostics formats, ensuring compatibility with different APIM logging configurations.

All visualizations are dynamically filtered by the selected APIM resource and time range, providing focused insights for the chosen service.

## Requirements

- Azure API Management service with diagnostic logs enabled
- Log Analytics workspace connected to your APIM service
- Appropriate permissions to read APIM metrics and logs

## Schema

This workbook uses the Azure Monitor Workbooks gallery template schema, making it compatible with the Azure portal workbooks experience.