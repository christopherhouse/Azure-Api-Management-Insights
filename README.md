# Azure API Management Insights

This repository contains an Azure Workbook for monitoring and analyzing Azure API Management (APIM) resources.

## Workbook Features

The `azure-api-management-insights.json` workbook provides comprehensive monitoring capabilities for Azure API Management services including:

### Parameters
- **Subscription Selection**: Choose the Azure subscription containing your APIM resources
- **Resource Group Selection**: Select the resource group containing your APIM service
- **API Management Service Selection**: Pick the specific APIM service to monitor
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
2. Select your subscription, resource group, and APIM service
3. Choose your desired time range (defaults to last hour)
4. View comprehensive metrics and logs for your APIM service

## Requirements

- Azure API Management service with diagnostic logs enabled
- Log Analytics workspace connected to your APIM service
- Appropriate permissions to read APIM metrics and logs

## Schema

This workbook uses the Azure Monitor Workbooks gallery template schema, making it compatible with the Azure portal workbooks experience.