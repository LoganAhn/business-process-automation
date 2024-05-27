# Whisper Preview Added - Check the env vars in the backend.  WHISPER_MODEL is hardcoded to the eastus region.  For any other region this will need to be manually updated.

# Business Process Automation Accelerator

## Overview

This accelerator provides a no code Studio for users to quickly build complex, multi-stage AI pipelines across multiple Azure AI and ML Services.  Users can select, and stack, AI/ML Services from across Azure Cognitive Services (OpenAI, Speech, Language, Form Recognizer, ReadAPI), Azure Machine Learning into a **single**, fully integrated **pipeline**. Integration between services is automated by BPA, and once deployed, a web app is created. This customizable UI&ast; provides and drag-n-drop interface for end users to build multi service pipelines. Finally, the user-created pipeline is triggered as soon as the first input file(s) are uploaded, storing the results in a Azure Blob Storage.


## Deploy to Azure Instructions

### Prerequisities
1. Github account (Admin)
2. Azure Resource Group (Owner)
3. Ensure your subscription has **Microsoft.DocumentDB enabled**  
4. Ensure that you have **accepted terms and conditions for Responsible AI**:  
You must initiate the creation of a "Cognitive services multi-service account" from the Azure portal to review and acknowledge the terms and conditions. You can do so here: [Quickstart: Create a Cognitive Services resource using the Azure portal](https://docs.microsoft.com/en-us/azure/cognitive-services/cognitive-services-apis-create-account?tabs=multiservice%2Cwindows).  
Once accepted, you can create subsequent resources using any deployment tool (SDK, CLI, or ARM template, etc) under the same Azure subscription.

1. Get a Workflow Level Token 
2. Fork the repository to a git account of which you are the Admin.
3. Click on the "Deploy to Azure" Button that corresponds to your environment and which patterns you wish to create.  
4. Only the Resource Group, Repo Token (from #2), and Forked Git Repo Url are needed.  The remaining parameters are filled in for you.
5. For a demonstration, please view the first Instructional Video at the top of this Readme.


### With OpenAI
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLoganAhn%2Fbusiness-process-automation%2Fmain%2Ftemplates%2Foneclickoai.json)

## Document Ingestion Architecture
Once you've created a high-level Resource Group, you'll fork this repository and importing helper libraries, taking advantage of Github Actions to deploy the set of Azure Cognitive Services and manage all of the new Azure module credentials, in the background, within your newly created pipeline. After pipeline deployment, a static webapp will be created with your newly customizable POC UI for building and triggering pipelines.

![](images/high-level-architecture-may-2023.png)  
*Document Ingestion High-level Technical Architecture*  

![](images/sample-pipelines-may-2023.png)  
*Several Sample Pipelines/Patterns Easily Created via the UI's drag-n-drop Interface*  
  
  
1. Pipeline #1: Two examples for creating a quick pipeline for ingesting **text** data, and then adding any of the Azure Language Services to process your text ([See all Azure Language Services Offerings here!](https://learn.microsoft.com/en-us/azure/cognitive-services/language-service/overview)), before visualizing in provided WebApp. The second pattern starts from ingestion of video data, and then adding any of our Video Analyzing Services to process your video! ([See all Azure Video Analyzer Services Offerings here!](https://azure.microsoft.com/en-us/products/video-indexer))

2. Pipeline #2: Quickly create a pipeline leveraging **multiple** Cognitive Services. In this sample pipeline, you can ingest **audio**, transcriber or transliterate with the Azure Speech Service [See all available Azure Speech Services here!](https://learn.microsoft.com/en-us/azure/cognitive-services/speech-service/overview), the resulting **text** output will be further extracted / transformed with Azure Language Service, and add another analysis layer with Azure OpenAI models.  

3. Our third sample pipeline is inspired from the [popular Enterprise ChatGPT demo](https://github.com/Azure-Samples/azure-search-openai-demo), providing the backend and popular UI for creating a ChatGPT-like experience over your own data.  

4. Pipeline #4: Popular approach for information retrieval with your own documents using a **vector store** and ChatGPT! Document chunking and vector store implementation is handled by the backend after you create your own pipeline.  
