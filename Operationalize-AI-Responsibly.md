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

There are three types of **filters** offered by Azure AI Content Safety:

- We provide configurable **content filters** for **harmful content**, like text and imagery containing violence or hate speech, which you can adjust by severity level. These are always set to a medium threshold by default.
- Customers can also create their own **custom content filters** using small training datasets.
- **Prompt shields** are detection models that can be turned on for model inputs, to detect when a user is trying to attack or manipulate the AI system into doing something outside it’s intended purpose or design.
- Lastly, we have **detection models** that can be turned on to flag other kinds of risky inputs or outputs, such as **protected or copyright material or code**, or **hallucinations**, where the model output does not align to the source material provided.
- Customers can also create custom blocklists to filters specific terms in inputs or outputs.

![Filters](https://github.com/codess-aus/Operationalize-AI-Responsibly/blob/2faa396596693c4b863ac09de041ca9a0ecb7f16/images/Filters.jpg)

## Steer your model’s behavior with a system message

Craft your system message to guide the model’s behavior and how it uses grounding data.

Spell out the **capabilities** that the agent should take on:
- Define the specific task(s) you would like the model to complete.
- Describe who the users of the model will be, what inputs will be provided to the model, and what you expect the model to output
- Define how the model should complete the tasks, including any additional tools (like APIs, code, plug-ins) the model can use.
- Define the scope and limitations of the model’s performance by providing clear instructions
- Define the posture and tone the model should exhibit in its responses.

Define the models **output format**:
- Define the language and syntax of the output format. For example, if you want the output to be machine parseable, you may want to structure the output to be in JSON, XSON or XML. 
- Define any styling or formatting preferences for better user readability like bulleting or bolding certain parts of the response

**Few shot learning**:
- Describe **difficult use cases** where the prompt is ambiguous or complicated, to give the model additional visibility into how to approach such cases.  
- Show **chain-of-thought reasoning** to better inform the model on the steps it should take to achieve the desired outcomes. 

**Safety Guardrails**:
- Define specific guardrails to mitigate harms that have been identified and prioritized for the scenario


 









