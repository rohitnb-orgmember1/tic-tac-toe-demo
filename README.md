# ✖️ Tic Tac Toe Game  :o:

![CodeQL](https://github.com/RohitDemo/tic-tac-toe-demo/workflows/CodeQL/badge.svg?branch=master)

![Continuous Integration workflow](https://github.com/RohitDemo/tic-tac-toe-demo/workflows/Continuous%20Integration%20workflow/badge.svg?branch=master)

![Deploy to Cloud](https://github.com/RohitDemo/tic-tac-toe-demo/workflows/Deploy%20to%20Cloud/badge.svg?branch=master)

<img width="451" alt="Screenshot 2020-10-20 at 8 19 39 AM" src="https://user-images.githubusercontent.com/48172220/96537171-415d1f80-12b3-11eb-9744-4a20f488db04.png">

A simple JavaScript browser based game that uses:
1. HTML/CSS/JavaScript
2. GitHub Node CI workflow from the Actions starter template
3. AWS SAM/CloudFormation/Lambda for deployment

## YML configs used
- .github/workflows/node.js.yml: This is a simple CI workflow that 
  - Runs: `npm ci`, `npm run build` , `npm test` on node versions 10.x, 12.x, 14.x
  - Triggers: Push to master or when pull request with master

- .github/workflows/deploy-prod.yml: Deploys to cloud (AWS)
  - Flow: Build & Upload Artifact, Donwload Artifact and push to AWS CloudFormation. (OPT) Pushes a docker image and stores in packages
  - Triggers: Manual

- .github/aws-config.yml: Defines the S3 Bucket, CloudFormation stackname, region

- sam-template.yml: This is the SAM template that CloudFormation uses to spin up the serverless app. Tells CF where to find the JS file, CSS etc.
