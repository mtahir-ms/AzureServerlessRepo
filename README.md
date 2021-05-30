# AzureServerlessRepo
Azure Serverless Repository. 

- gZipLogicApp Directory has a generic function to process compress/decompress inputs. I developed it to integrate with Azure serverless products. It can actually be consumed by any cloud/on-prem process/APIs/Components. 

gZip compressions can be used to integrate two systems or just to process data faster. Compressed data size is smaller than original by 20 to 30%. Sometime business applications or source systems are producing/accepting gzip compressed / decompressed data. 

Azure Function will host this solution as HTTP Trigger. It has following simple requirements

Decompress : Pass it base64 compressed gZip string value. You will need to pass a JSON structure with two must to have fields {content-encoding:"gzip", content:"base64datastringetc"}. You should pass content encoding value in Headers, Howeever I kept a field in JSON structure to cover a missing header scenario. 

Compress: Pass it any string data, It will return compressed base64 string gzip data. 

