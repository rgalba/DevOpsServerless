# DevOps for Serverless

## Agenda
1. Introduction to serverless
2. DevOps definition
3. A real app
4. Applying DevOps to SLS

# Section 1: Introduction to serverless

> Serverless: run code without a server!

> “The serverless approach is a process where we deploy the code into a cloud and it is executed automatically, without worrying about the underlying infrastructure, renting or buying servers, scaling, monitoring, or capacity planning. The service provider will take care of all these things.”

>“Serverless computing will automatically provision and configure the server and then execute the code. As the traffic rises, it will scale automatically, apply the required resources, and scale down once the traffic eases down.”

Its like Uber: You don`t have to buy a car to be able to use one. I pay just when you will need one during the period that you need it.

### Backend as a service

The BaaS was conceptualized by Auth0 and Google Firebase. Basically, BaaS is third-party service through which we can implement our required functionality, and it will provide server-side logic for the implementation of the application.

Another BaaS service is Firebase, provided by Google. Firebase is a database service that is used by mobile apps, where database administration overhead is mitigated, and it provides authorization for different types of users.

> BaaS address an specific requirement functionality and delivers it in a serverless model.

### Function as a service

“Serverless also means code that is developed to be event-triggered, and which is executed in stateless compute containers.”

“So, in FaaS architecture, we break our app into small, self-contained programs or functions instead of the monolithic app that runs on PaaS and performs multiple functions.”

“The benefit to breaking down an application into functions is that we can scale and deploy each function separately.”

#### FaaS x PaaS
- In a FaaS system, start within milliseconds handling individual requests.
- In PaaS systems, application thread that keeps running for long periods of time, and handles multiple requests.

- FaaS services are charged per execution time of the function
- PaaS services are charged per running time of the thread in which the server application is running.

#### Providers

- AWS Lambda
- Azure Functions
- Google Functions
- IBM OpenWhisk

### Pros

- Faster timer to market
- Highly scalable
- Optimized cost
- Latency and geolocation improvement (edge computing)

### Cons

- Increased complexity
- Lack of tolling
- Complexity with architecture
- Drawback in implementation
---
# Section 2: DevOps Definition

> *Devops is just CI/CD.*

*DevOps is a collaboration of tools, processes, and feedback.*

DevOps is a safety way to deploy even for user than for developers.

- Automation to decrease project`s complexity
- Continous integration (protect devs against themselves)
- Logging or monitoring apps(functions)
- Continuous testing before production
- Release management
- Monitoring, alarms and metrics

# Section 3: A real app

application: TODO list API
stack:
- AWS Lambda
- Serverless framework
- DynamoDB
- Python

### Why to use a serverless framework?

- Simplify deployment
- Version control infrastructure and resources definition
- Release management (rollout and rollback)
- Multi language support
- Manage a single function or a whole service
- Plugins
- Metrics
- Multi environment control

### Talk is cheap. Show me the `manifest.yml`

[manifest.yml](./serverless.yml)

### Section 4: Applying DevOps to a serverless app

#### Deployment of a Lambda function
```sh
aws configure
cd DevOpsServerless
sls deploy
```

- AWS Lambda with DevOps
- Serverless with CodeStar
- Blue and green deployment with AWS Lambda
- The GitHub and Jenkins pipeline using Serverless Framework
- Setting up Jenkins for a serverless application


---
references

- “DevOps for Serverless Applications. Shashikant Bangera”
- https://github.com/nerdguru/serverlessTodos/blob/master/docs/codePipeline.md