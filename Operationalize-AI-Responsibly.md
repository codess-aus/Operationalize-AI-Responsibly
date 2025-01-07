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

## So what type of risks do we see most often in in generative AI systems?

The first category of risk is overall quality of the application. 
We want to ensure that the application is not producing errors or what people often call **hallucinating**, which would be like adding additional incorrect information or just sort of making up information.

We also need to make sure that our system is robust to adversarial attacks.
This could be a **jailbreak**, which is when a user tries to manipulate or confuse the system to get it to produce something that it’s not supposed to produce, or new types of attacks where an attacker embeds hidden instructions in data sources like emails or documents (**prompt injection**).

We also look at traditional **harmful content**, whether that is harmful natural language content, for example, or harmful imagery or code that contains security vulnerabilities.

Then one of the newer areas that's emerging is that these models can seem **very human-like** when interacting with end users. 
When is it okay for a system to be conversing and acting like a human? And when is that going to be misleading, inappropriate, or harmful?

So, you need to be looking across all of these different dimensions, which may sound like a lot, but we’ve found that same technological approach works for each of these different types of attacks.

## Risk mitigation layers

We find that most production applications require a mitigation plan with four layers of technical mitigations: (1) the model, (2) safety system, (3) system message and grounding, and (4) user experience layers. 

![Defence in Depth](https://github.com/codess-aus/Operationalize-AI-Responsibly/blob/9c4f0bffbff7e9c4ecde9735f4f8abc09ca0ec6b/images/defenceindepth.jpg)

The model and safety system layers are typically platform layers, where built-in mitigations would be common across many applications. They are built into Azure for you. 

The next two layers largely depend on the application’s purpose and design, meaning the implementation of mitigations can vary a lot from one application to the next. 

Note that, while the foundation model you’re using is obviously an important component of the system, it's not the complete system. For most applications, it’s not enough to rely on the **safety mitigations built into the model itself**. Even with fine-tuning, LLMs can make mistakes and are susceptible to attacks like jailbreaks.

So, just like security, at Microsoft we use a layered defense-in-depth approach. 
And we apply an AI-based **safety system** that goes around the model and monitors the inputs and outputs to help prevent attacks from being successful and catches places where the model makes a mistake.
At Microsoft, this state-of-the-art safety system is called **Azure AI Content Safety**.

And the filters are configurable for inputs and outputs… because you might want different settings for your use case. For example, a gaming company may be more permissive of violent language in inputs but may not want to output violent language to users.

We’ve integrated this service directly into our Microsoft Copilot ecosystem as a built-in safety system, and we make the same technology available to developers via Azure AI to help them build safer AI applications from the start.

![Azure Content Safety](https://github.com/codess-aus/Operationalize-AI-Responsibly/blob/0bc86e55ca482063fcf8a84796036b575f4b6820/images/safetysystem.jpg)











