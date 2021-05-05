---
title: "Swagger"
weight: 2
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: true
---

<!--more-->

## Abstract
Swagger is the most popular API development tool. It follows the OpenAPI Specification (OpenAPI Specification, also referred to as OAS).It can run through the entire API ecosystem, such as API design, API documentation, testing, and deployment.

### Support Specification
- [Swagger 2.0](https://swagger.io/docs/specification/2-0/basic-structure/)
- [Openapi 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md)

### Support Grammer
- [Json](https://en.wikipedia.org/wiki/JSON)
- [Yaml](https://en.wikipedia.org/wiki/YAML)

### Tool
- Swagger Editer: an editor for writing Swagger documents, and also supports real-time document detection, API debugging and other functions.
- Swagger UI: a UI rendering tool used to render Swagger documents to provide a beautiful API interface.
- Swagger-codegen: a code generator that can build server-side stubs and client-side SDKs based on Swagger documents.

## Preparation
The Server need to support OCRS(Cross-origin resource sharing)
Basic Thoughts:
- Add response header in each request:
```
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, POST, PUT, DELETE, OPTIONS
Access-Control-Allow-Headers: Content-Type, Key, Authorization
```
- Add OPTION method support: return 200 OK with the headers as below.

## Swagger Editor
Swagger-editor is a API editor, mainly used to write Swagger Document (RESTful API documents that comply with Swagger specifications).

### Funtionality
- Write Swagger documentation
- Real-time detection of whether the Swagger document complies with the Swagger specification
- Debug the API interface described in the Swagger document
- Convert Swagger documents (yaml to json, or json to yaml)

### Deployment
```bash
docker run -d -p 8080:8080 --name swagger-editor  swaggerapi/swagger-editor
```

### Usage
Open the website **http://127.0.0.1:8080** in browers, then you can import/create your Openapi document.

## Swagger UI
A set of HTML/CSS/JS framework for rendering Swagger documents to provide a beautiful API document interface.

### Deployment
```bash
docker run -d -p 8081:8080 --name swagger-ui -v $(pwd):/usr/share/nginx/html/config swaggerapi/swagger-ui
```

### Usage
Open the website **http://127.0.0.1:8081** in browers.Chane the title to the json/yaml path that you mount, example: **./config/openapi.yaml**

## Gitlab Support
1. Copy the OpenAPI document to the project
2. change the document name start with "openapi" (not case sensitive)
3. commit the change to the gitlab. 
4. Open the Gitlab in brower, open the document you commit.

If the openAPI document include the other openapi document, you should do something like the following example.

Example Situation:`OPENAPI-TS29503_Nudm_SDM.yaml` will include `TS29571_CommonData.yaml`
- copy the `TS29571_CommonData.yaml` to the project
- change the name to `OPENAPI-TS29571_CommonData.yaml`
- replace all string from `TS29571_CommonData.yaml` to `OPENAPI-TS29571_CommonData.yaml` in `OPENAPI-TS29503_Nudm_SDM.yaml`, if `OPENAPI-TS29571_CommonData.yaml` and `OPENAPI-TS29503_Nudm_SDM.yaml` in different path, that you should add the relative path before `OPENAPI-TS29503_Nudm_SDM.yaml`, like `../OPENAPI-TS29503_Nudm_SDM.yaml`

## Reference
- [Swagger](https://swagger.io/docs/)
