<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create an API for Your RAG Chatbot

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-rag-api)

**Author:** Albert  
**Email:** tapcyberx@gmail.com

---

## How I Built an API for My RAG Chatbot

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_r4s5t6u7)

---

## Introducing Today's Project!

In this project, I will demonstrate how to set up an API for your RAG chatbot. I'm doing this project to learn how RAG chatbot can work with different technologies and how can you adapt as you need it from another perspective with your own information.

### Tools and concepts

Services I used were Amazon Bedrock, Amazon S3, Amazon IAM, Git. Key concepts I learnt include how APIs work, different API endpoints, environment variables, importing and installing dependencies.

### Project reflection

This project took me approximately 3H to complete the all process. The most challenging part was dealing with PowerShell (errors). It was most rewarding to never give up in how I find the solutions to every problem that I wasn't expected in this project.

I chose to do this project today because I always like to improve my knowledge in hand- on project like this.

---

## Setting Up The Knowledge Base

To set up my Knowledge Base, I used S3 to store our documents. These documents I uploaded contain information about projects that I need for my chatbot knowledge.

Amazon Bedrock is an AWS service that lets you use powerful AI models to build generative AI applications. 
A Knowledge Base in Bedrock was created to store all information your chatbot needs, organizing it for easy retrieval and enabling the chatbot to quickly find relevant information in response to questions.

My chatbot also needs access to two AI models to Titan Text Embeddings V2 and Llama 3.3 70B Instruct. I then synchronized with my S3 bucket in the data source because we need to read those documents from S3, process to understand the meaning of the words inside them, and store the processed information in the OpenSearch vector database.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_1u2v3w4x)

---

## Running CLI Commands Locally

When I ran a Bedrock command in my terminal, I initially got an error because it wasn't have the proper information like knowledgeBaseId/modelArn To resolve this, I just uodated with the right information.

---

## Running Bedrock Commands

When I first ran a Bedrock command, I ran into an error because I needed to provide values for Knowledge Base ID and Model ARN

To find the required values, I had to revisit the AWS managmment console, to find the knowledge Base ID and to find the Model ID and ran another command to find the model ARN The Bedrock command ran successfully and showed me the proper chat respond after I run a couple errors.

---

## Creating an API

An API is an Application Programming Interface that acts as a bridge between applications or external servers. The API I’m creating will connect to Amazon Bedrock to make the chatbot respond to our requests. This will help test our chatbot by automating response generations.

The API code has three main sections: importing library dependencies, loading environment variables, and defining the features of the API endpoints.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_w7x8y9z0)

---

## Installing Packages

To run the API, I had to install requirements like fastapi, boto3, python-dotenv, and uvicorn. 
These packages are important because they helps us to run the API and loading the evironments variables. 



![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_a8b9c0d1)

---

## Testing the API

When I visited the root endpoint, I saw a message that says {"message": "Welcome to your RAG chatbot API"}  This confirms that our API is working and accesible. This message its similar as I defined before in the main.py file.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_i6j7k8l9)

---

## The Query Endpoint

The query endpoint connects an app with the chatbot I tested the query endpoint by appending bedrock/query?text=What%20is%20NextWork to the URL , The response was an error Parameter validation failed because I still don't define Knowledge Base ID and Model Arn.



Looking at the API code, I can see that the API calls for environment variables because writing sensitive information in your code isn't a best practice. To resolve the error in my query endpoint, I need to replace those variables with the right ones.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/ai-rag-api_r4s5t6u7)

---

## Extending the API

---

---
