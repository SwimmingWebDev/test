# What is IaC

### Infrastructure as Code (IaC)

- a mainstream pattern for managing [infrastructure](Glossary%20af29591a425e40ed88168e70e015ec89.md) with [configuration files](Glossary%20af29591a425e40ed88168e70e015ec89.md) rather than through a graphical user interface or manual command line script
- It allows you to build, change, and manage your infrastructure in a safe, consistent, trackable, and repeatable way by defining resource configurations that you can version (in a version control system like GitHub), reuse, and share
- designed to be a systematic approach are best adopted as a framework

### IaC principle

<aside>
👉 **always produce the same result**

</aside>

- sets the target environment into the same configuration, regardless of the environment's starting state

### Why IaC use

<aside>
🔥 What happens if you need to deploy your application on 10,50 or 100 more machines?

</aside>

⇒ reduces operational overhead and risk of managing or changing infrastructure

- **Increase productivity**
    
    → Speed up infrastructure provisioning by **automating tasks** and **eliminating manual configuration**
    
- **Improved consistency and Accuracy**
    
    → eliminates the human error that results in countless breaches and security risks 
    
- **Scalability and Flexibility**
- **Version Control and Documentation**
    - Creating trackable and auditable configurations by enabling version-controlled infrastructure and configuration modifications

### IaC [Continuous Integration](Glossary%20af29591a425e40ed88168e70e015ec89.md) / [Continuous Delivery](Glossary%20af29591a425e40ed88168e70e015ec89.md)

- Proof that the change was successful and that the application is working as expected
- All environments (Dev, Pre-Prod and Prod) are updated and remain in-sync
- Deployment to any environment (on-prem, cloud, or edge) can be automated
- Supporting tasks (provisioning, testing, auditing, etc.) are automated
- Delivery of supporting tools and platforms is automated
- Security and compliance concerns are addressed

### **Declarative definition files**

<aside>
💡 IaC should use declarative definition files if possible

</aside>

- what is a declarative definition file?
    - a configuration file that specifies the desired state of the infrastructure without explicitly defining the steps needed to achieve that state Instead of focusing on the procedural details of how resources should be provisioned or configured
        
        → allows for greater flexibility to use optimized techniques the infrastructure provider supplies
        
- help reduce the technical debt of maintaining imperative code
- No standard syntax for declarative IaC. Different platforms support file formats such as YAML, JSON, and XML.
- example
    - Terraform ****(HashiCorp Configuration Language - HCL)
        
        ```
        resource "aws_instance" "example" {
        ami           = "ami-0c55b159cbfafe1f0"
        instance_type = "t2.micro"
        }
        ```
        
    - Ansible (YAML)
        
        ```yaml
        ---
        - name: Install and start Apache
          hosts: web_servers
          tasks:
            - name: Install Apache
              yum:
                name: httpd
                state: present
            - name: Start Apache
              service:
                name: httpd
                state: started
        ```
        
    - Puppet (Puppet [Domain-Specific Language](Glossary%20af29591a425e40ed88168e70e015ec89.md))
        
        ```yaml
        package { 'apache2':
          ensure => installed,
        }
        
        service { 'apache2':
          ensure => running,
        }
        ```
        
    - SaltStack (YAML State File with Jinja Templating)
        
        ```yaml
        apache2:
          pkg.installed
        
        apache_service:
          service.running:
            - require:
              - pkg: apache2
        ```