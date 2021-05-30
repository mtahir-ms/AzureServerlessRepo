# gZIP Azure Function (Compression/Decompression)
gZIP Azure Function / Logic Apps (Compression/Decompression). 

- gZipLogicApp Directory has a generic function to process compress/decompress inputs. I developed it to integrate with Azure serverless products. It can actually be consumed by any cloud/on-prem process/APIs/Components. 

gZip compressions can be used to integrate two systems or just to process data faster. Compressed data size is smaller than original by 20 to 30%. Sometime business applications or source systems are producing/accepting gzip compressed / decompressed data.  It can be used in multiple scenarios/platform components. For example, I can use it in Logic App or simply use it in any other trigger of functions/logic app/event hub/service bus/data factory. We have data ingestion happening in multiple layers. This Azure function can be used seamlessly to perform gZip operations.
 
gZipServerlessAzureFunction.cs has the neat code with comments.

Azure Function will host this solution as HTTP Trigger. It has following simple requirements

Decompress : Pass it base64 compressed gZip string value. You will need to pass a JSON structure with two must to have fields {content-encoding:"gzip", content:"base64datastringetc"}. You should pass content encoding value in Headers, Howeever I kept a field in JSON structure to cover a missing header scenario. 

Compress: Pass it any string data, It will return compressed base64 string gzip data. 

An example of how to use this function in Logic Apps 

![image](https://user-images.githubusercontent.com/73873314/120121248-f61fbf00-c167-11eb-9890-f6ce6a66a3e5.png)
