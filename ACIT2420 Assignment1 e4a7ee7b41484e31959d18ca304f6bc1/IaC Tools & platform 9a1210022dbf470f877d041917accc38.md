# IaC Tools & platform

### What is [IaC Framework](Glossary%20af29591a425e40ed88168e70e015ec89.md)

- provides a comprehensive set of guidelines, best practices, and conventions for managing infrastructure as code
- enable developers and operations teams to define infrastructure requirements using code, such as declarative configuration files or scripts, rather than manual processes or manual configuration
- Example of IaC Framework
    
    → AWS Cloud Development Kit (CDK), Azure Resource Manager (ARM) templates, and Google Cloud Deployment Manager
    

### What is IaC Tool

- a specific software application or utility designed to automate the provisioning, configuration, and management of infrastructure resources using code
- provide a domain-specific language (DSL) or configuration format for defining infrastructure configurations, as well as a runtime environment for executing those configurations
- example of IaC Tool

| Tool | Pros | Cons | Language |
| --- | --- | --- | --- |
| Terraform
 | • easy-to-read configurations
• Large provider support for various cloud platforms
• Modular design for reusable configurations | • Learning HCL syntax
• Complexity with large deployments | HCL, JSON |
| Ansible | • easy deployment
• Simple YAML syntax for configuration files
• Support for managing diverse infrastructure environments | • Limited built-in support for cloud resource provisioning
•  Slower execution compared to compiled languages | YAML, Jinja2 |
| Chef | • Powerful DSL for configuration management
• Strong community and ecosystem support
• Test-driven development with ChefSpec and InSpec | •  Learning curve for Ruby DSL and Chef's terminology
•  Requires more setup and configuration compared to simpler tools | Ruby DSL, Chef Infra Language (CIL) |
| Puppet
(Agent-based tool) | • Declarative language for infrastructure configuration
• Large module ecosystem for extending functionality
• Support for role-based access control (RBAC) | • Steeper learning curve for Puppet DSL
•  Performance overhead in larger environments due to agent-based architecture | Puppet DSL |
| SaltStack | • Event-driven automation for real-time responses
•  Highly scalable with distributed architecture
• Flexible execution modes for agentless or agent-based operations | •  Complex setup and configuration for larger deployments
•  May require more resources for master-minion architecture | YAML, Jinja2 |

### [Agent](Glossary%20af29591a425e40ed88168e70e015ec89.md) vs [Agentless](Glossary%20af29591a425e40ed88168e70e015ec89.md) based tool

- Agent-based tool ( Puppet)
    - require the user to install a piece of software on each device that needs to be managed
    - communicates over encrypted communications methods to a controlling ‘master’ device
    - Disadvantage
        - a reduction in flexibility if simple ad-hoc changes need to be made to one or just a small number of machines
- Agentless based tool (Puppet Bolt and Ansible)
    - do not require agents to be installed to manage machines and communicate via protocols such as SSH and WinRM
    - great for when quick and easy deployments need to be made
    - Disadvanage
        - no way of reporting back on a machine’s current state and/or enforcing a desired state to make sure it is compliant
        - concerns around security when using communication protocols such as SSH and WinRM

### Template-based Tools

- provide simplicity and native integration with specific cloud platforms
- have limitations in expressing complex dependencies and orchestrating multi-step deployment processes
- AWS CloudFormation, Azure Resource Manager, and Google Cloud Deployment Manager