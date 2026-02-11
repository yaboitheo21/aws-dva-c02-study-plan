# AWS Certified Developer Associate DVA-C02 Study Plan

A comprehensive, structured study guide for the AWS Certified Developer Associate (DVA-C02) exam. This resource covers all four exam domains with detailed theory notes, hands-on labs, and practice question placeholders organized by official AWS Exam Guide skills.

## About This Project

This study plan is built as a Hugo static site using the hugo-theme-learn template, styled to match the AWS First Cloud Journey (FCJ) workshop format. It maps all 101 skills from the official DVA-C02 Exam Guide into a navigable, topic-based learning path.

### Exam Overview

| Detail | Value |
|--------|-------|
| Exam Code | DVA-C02 |
| Duration | 130 minutes |
| Questions | 65 multiple choice and multiple response |
| Passing Score | 720 out of 1000 |
| Exam Fee | 150 USD |

## Content Domains

| Domain | Weight | Theory Files | Hands-on Labs |
|--------|--------|-------------|---------------|
| Domain 1 - Development with AWS Services | 32% | 3 sections, 29 skills | 7 labs |
| Domain 2 - Security | 26% | 3 sections, 21 skills | 5 labs |
| Domain 3 - Deployment | 24% | 4 sections, 27 skills | 6 labs |
| Domain 4 - Troubleshooting and Optimization | 18% | 3 sections, 24 skills | 5 labs |

## Key Topics Covered

- AWS Lambda, API Gateway, DynamoDB, S3, SQS, SNS, EventBridge, Kinesis
- IAM, Cognito, KMS, Secrets Manager, STS, encryption patterns
- CodePipeline, CodeBuild, CodeDeploy, CloudFormation, SAM, CDK, ECS, Fargate
- CloudWatch, X-Ray, caching strategies, performance optimization
- Deployment strategies including blue-green, canary, rolling, and immutable
- Event-driven architecture, microservices, fan-out patterns
- CI/CD pipelines, infrastructure as code, container deployments

## Suggested Study Timeline

- Week 1-2: Domain 1 - Development with AWS Services (32 percent weight)
- Week 3: Domain 2 - Security (26 percent weight)
- Week 4: Domain 3 - Deployment (24 percent weight)
- Week 5: Domain 4 - Troubleshooting and Optimization (18 percent weight)
- Week 6: Review, mock exams, and weak area reinforcement

## Reference Materials

- Stephane Maarek Ultimate AWS Certified Developer Associate course on Udemy
- AWS Official Exam Guide for DVA-C02
- AWS Skill Builder free practice exams
- AWS Documentation

## Run Locally

Prerequisites: Hugo Extended v0.120.4 or compatible version, Git.

```bash
git clone https://github.com/ihatesea69/aws-dva-c02-study-plan.git
cd aws-dva-c02-study-plan
git submodule update --init --recursive
hugo server -D
```

Open http://localhost:1313/aws-dva-c02-study-plan/ in your browser.

## Deploy

This site is deployed to GitHub Pages using GitHub Actions. Push to the main branch triggers automatic build and deployment.

## Project Structure

```
content/
  1-domain1/    Development with AWS Services (theory, labs, questions)
  2-domain2/    Security (theory, labs, questions)
  3-domain3/    Deployment (theory, labs, questions)
  4-domain4/    Troubleshooting and Optimization (theory, labs, questions)
  5-aws-services/   In-scope AWS services reference
  6-study-plan/     Suggested 6-week study timeline
static/
  css/          Custom AWS-style theme
layouts/
  partials/     Custom logo and sidebar footer
```

## License

This project is for personal educational use. AWS, the AWS logo, and all AWS service names are trademarks of Amazon Web Services, Inc.
