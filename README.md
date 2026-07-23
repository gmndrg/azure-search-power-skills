![python](https://img.shields.io/badge/language-python-orange)
![C#](https://img.shields.io/badge/language-C%23-brightgreen)

> [!IMPORTANT]  
> As of November 15, 2023, Azure Cognitive Search has been renamed to Azure AI Search.

# Azure AI Search Power Skills

Power Skills are a collection of useful functions to be deployed as custom skills for Azure AI Search. The skills can be used as [templates](Template/HelloWorld/README.md) or starting points for your own custom skills.

## Skills

This project provides the following custom skills:


| Skill | Description | Type |Language | Environment |Deployment|
| --- | ----------- | -------| ----------- | ----------- | ----------- |
| [Chat completion Custom Skill](ChatCompletionCustomSkill/README.md) | Demonstrates how to use chat-completion inference capabilities of language models (including Azure OpenAI models) deployed in Azure AI Foundry. | Text | ![python](https://img.shields.io/badge/language-python-orange) | Azure Functions | |
| [GeoPointFromName](Geo/GeoPointFromName/README.md) | Retrieves coordinates from place names and addresses. | Geography | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [Distinct](Text/Distinct/README.md) | De-duplicates a list of terms. | Text | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [TextAnalyticsForHealth](Text/TextAnalyticsForHealth/README.md) | A wrapper for the Text Analytics for Health API. | Text | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [TextQualityWatchdog](Text/TextQualityWatchdog/README.md) | Uses a pretrained language model to detect low-quality text extracted during document cracking. | Text | ![python](https://img.shields.io/badge/language-python-orange) | Docker | |
| [DecryptBlobFile](Utils/DecryptBlobFile/README.md) | Downloads, decrypts, and returns a file previously encrypted and stored in Azure Blob Storage. | Utility | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [GetFileExtension](Utils/GetFileExtension/README.md) | Returns the filename and extension as separate values to allow filtering on document type. | Utility | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [HelloWorld](Template/HelloWorld/README.md) | A minimal skill that can be used as a starting point or template for your own skills. | Template | ![C#](https://img.shields.io/badge/language-C%23-brightgreen) | Azure Functions | |
| [PythonFastAPI](Template/PythonFastAPI/README.md) | A production web server and API scaffold for a Python power skill. | Template | ![python](https://img.shields.io/badge/language-python-orange) | Azure Functions | |



## Getting Started

### Prerequisites

In order to use the functions in this project, you'll need an active Azure subscription. Most of the functions can be used on their own for quick evaluation and experimentation, but they are meant to be used as custom skills in Azure AI Search.
Each function may also add its own specific requirements, such as API keys for services they leverage.

[Visual Studio](https://visualstudio.microsoft.com/) is recommended, but not required. You need a recent version of the C# compiler. [Postman](https://www.getpostman.com/) is highly recommended as a way to test your functions.

### Installation and deployment

If using Visual Studio with the Azure workload installed, no installation is required, and the functions can just be run locally using F5.

Deployment of a function to Azure can be done [through Visual Studio](https://docs.microsoft.com/azure/azure-functions/deployment-zip-push), the Deploy to Azure button, or [continuous deployment](https://docs.microsoft.com/azure/azure-functions/functions-continuous-deployment).

Some functions may require setting environment variables or configuration entries. Please refer to the readme file in the function's directory.

### Quickstart

1. Clone the repository
2. Open the PowerSkills solution in Visual Studio
3. Set the project for the function to test as the startup project
4. Hit F5
5. Experiment with calling the function using Postman

You can also create your own skills using [our Hello World template skill](Template/HelloWorld/README.md) as a starting point 
or if you are using python [our FastAPI template skill](Template/PythonFastAPI/README.md).

## Up for grabs

Here are a few suggestions of simple contributions to get you started:
* Improve documentation: sample code, better documentation are great ways to improve your understanding of existing code and to help other do the same.
* Configuration: some skills can be configured through [application settings and environment variables](https://github.com/Azure-Samples/azure-search-power-skills/blob/main/Vision/AnalyzeForm/AnalyzeForm.cs#L31-L37).
* For skills that rely on an external Azure resource (such as [Bing Entity Search](https://github.com/Azure-Samples/azure-search-power-skills/blob/main/Text/BingEntitySearch/BingEntitySearch.cs#L20)), use [managed identities](https://learn.microsoft.com/azure/active-directory/managed-identities-azure-resources/overview) to avoid including keys in your solution.

## Resources

- [Contribution guidelines](CONTRIBUTING.md)
- [Azure Search](https://azure.microsoft.com/services/search/)
- [Azure Functions](https://azure.microsoft.com/services/functions/)
- [JFK Files](https://github.com/microsoft/AzureSearch_JFK_Files)
- [Knowledge Mining Solution Accelerator Guide](https://github.com/Azure-Samples/azure-search-knowledge-mining)
