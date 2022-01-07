service: aws-node-project-api

frameworkVersion: '2 || 3'

plugins:
  - serverless-api-client-certificate

provider:
  name: aws
  runtime: nodejs12.x
  lambdaHashingVersion: 20201221

functions:
  hello:
    handler: handler.hello
    events:
      - http: GET hello

custom:
  serverlessApiClientCertificate:
    rotateCerts: true
    daysLeft: 30
