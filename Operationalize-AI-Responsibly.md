# Operationalize AI Responsibly

Developers should aim to build a repeatable, systematic process to ensure consistency at scale.

![Lifecycle](https://github.com/codess-aus/Operationalize-AI-Responsibly/blob/693f55dd6876ab8b616844b5f97685eb8ed8d87b/images/generative-ai-lifecycle.png)

## Governance
Establish policies, practices, and processes that align with Microsoft's Responsible AI Standard. 
It includes embedding AI principles into the development lifecycle and workflows to comply with laws and regulations across privacy, security, and responsible AI.

## Map
Potential risks are identified and prioritized. 
This includes conducting impact assessments, security threat modeling, and red teaming to understand the implications of the AI system on people, organizations, and society.

## Measure
The frequency and severity of potential harms are measured using clear metrics, test sets, and systematic testing. 
This helps in understanding the trade-offs between different kinds of errors and experiences.

## Mitigate
Mitigations are implemented using strategies like prompt engineering, grounding, and content filters. 
The effectiveness of these mitigations is then tested through manual and automated evaluations.

## Operate
Define and execute a deployment and operational readiness plan, setup monitoring, and improve the AI application in production through monitoring and incident response.

![risks](https://github.com/codess-aus/Operationalize-AI-Responsibly/blob/76ffc1a0326ccffd544b02d9e8a0598a11cd708e/images/risks.jpg)

So what type of risks do we see most often in in generative AI systems?
The first category of risk is overall quality of the application. 
We want to ensure that the application is not producing errors or what people often call **hallucinating**, which would be like adding additional incorrect information or just sort of making up information.

We also need to make sure that our system is robust to adversarial attacks.
This could be a **jailbreak**, which is when a user tries to manipulate or confuse the system to get it to produce something that it’s not supposed to produce, or new types of attacks where an attacker embeds hidden instructions in data sources like emails or documents.

We also look at traditional **harmful content**, whether that is harmful natural language content, for example, or harmful imagery or code that contains security vulnerabilities.

Then one of the newer areas that's emerging is that these models can seem **very human-like** when interacting with end users. 
When is it okay for a system to be conversing and acting like a human? And when is that going to be misleading, inappropriate, or harmful?

So, you need to be looking across all of these different dimensions, which may sound like a lot, but we’ve found that same technological approach works for each of these different types of attacks.








