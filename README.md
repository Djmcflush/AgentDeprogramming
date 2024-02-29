# AgentDeprogramming
Deprogramming Sleeper Agents using Adapters! (Explaining why Adversarial Training is Useless against them)

## Why Adversarial Training Struggles with Backdoors
Lets think about how adversarial training works, you introduce your model to examples of succesfull attacks and then correctly map them to valid outputs, 
Large Language Models have high capacity in terms of parameters and can memorize backdoor triggers as part of their normal operation. Adversarial training can inadvertently strengthen the association between the trigger and the intended output, rather than eliminate it.


## Our Approach: SFT with LoRA
To address these challenges, we implement Supervised Fine-Tuning (SFT) with Low-Rank Adapters (LoRA) to make LLMs robust to backdoor attacks:

Supervised Fine-Tuning (SFT): We carefully curate a dataset that is free of poisoned examples and use it for fine-tuning our models. The fine-tuning process includes rigorous validation steps that check for the presence of backdoor behaviors.

Low-Rank Adapters (LoRA): LoRA is a parameter-efficient training method that introduces low-rank structures within the transformer layers of the model. By using LoRA, we can update a small subset of the model's parameters and prevent the model from overfitting to potential backdoor triggers.

Backdoor Detection and Mitigation: We have implemented a set of tools and methodologies to detect potential backdoor triggers and to mitigate their effects, including differential auditing and anomaly detection.

Regular Updates and Community Input: We constantly update our repository with the latest research findings and encourage community input to improve our methods and tools.


## Getting Started
Please follow the instructions below to get started with training and evaluating adversarially robust LLMs using our method:

Clone the Repository:

```
git clone https://github.com/your-repo/robust-llm.git
cd robust-llm
pip install -r requirements.txt
```
Prepare the Data:
Follow the instructions in data/README.md to set up your datasets.

## Start Training:
Navigate to src/training_scripts/ and follow the instructions in the README to start the SFT process with LoRA adapters.

## Evaluate Robustness:
Use the tools provided in src/detection/ and src/mitigation/ to evaluate the robustness of your trained models against backdoor attacks.

## Contribute:
We welcome contributions! Please read CONTRIBUTING.md for how to contribute to the project.


## Support and Contact
For support, questions, or to report an issue, please open an issue in the repository or contact the maintainers at contact@your-repo-domain.com.

## Acknowledgments
We would like to thank all the contributors and researchers in the field of adversarial machine learning for their insights and work, which have been instrumental in the development of this repository. Very specifically we would like to thank TDC 2023 for the data + base models used in this experiment! https://trojandetection.ai/
