# ExampleMetadatIpfsUpload
Metadata structure JSON example,  image and upload with Pinata CLI.

## Required 00: Pinata account [JWT]
Create an account and store your JWT.

## Required 01: Package pinata-cli
>npm i -g pinata-upload-cli

## Usage of pinata-cli
### Authenticate Public IPFS:
>pinata-cli -a [Pinata JWT]
### Authenticate Submarining:
>pinata-cli -as [Pinata V2 API Key]
### Upload a folder or file to public IPFS:
>pinata-cli -u ../../../test/folder/relative/path
### Upload a folder or file to private Pinata Submarine:
>pinata-cli -s ../../../test/folder/relative/path

        
# Create and upload your metadata
## Authenticate pinata-cli
>pinata-cli -a [Pinata JWT]

## Image upload
It's recommended to upload the image first:

>pinata-cli -u MetadataExampleImage
>{ percent: 0, transferred: 0, total: 6886 }
>{ percent: 0.026139994191112403, transferred: 180, total: 6886 }
>{ percent: 0.9915771129828638, transferred: 6828, total: 6886 }
>{ percent: 1, transferred: 6886, total: 6886 }
>Pinning, please wait...
>{
>  IpfsHash: 'QmdoNriSckXbb26WXLBRMz9dLPFnYAPV3xj1JR8i4LU24R',
>  PinSize: 6726,
>  Timestamp: '2022-09-02T06:40:51.555Z'
>}

## Check the hash and the resulting link
With a public gateway you can check your image by pasting the following construct to your browser:

>https://ipfs.io/ipfs/QmdoNriSckXbb26WXLBRMz9dLPFnYAPV3xj1JR8i4LU24R/?filename=metadata_example.png

## Create JSON file
It is recommended to follow the standards provided by opensea for metadata design (https://docs.opensea.io/docs/metadata-standards).

## JSON upload
After that paste the ipfs link as image into the metadata:

>pinata-cli -u MetadataExample
>{ percent: 0, transferred: 0, total: 1060 }
>{ percent: 0.17547169811320754, transferred: 186, total: 1060 }
>{ percent: 0.9452830188679245, transferred: 1002, total: 1060 }
>{ percent: 1, transferred: 1060, total: 1060 }
>Pinning, please wait...
>{
>  IpfsHash: 'QmUpQfUcd1zd7wDhm2YN8FMKeShK4vN3SBxkp3KaMxgvrj',
>  PinSize: 898,
>  Timestamp: '2022-09-02T06:50:15.944Z'
>}
