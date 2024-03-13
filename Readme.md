eagle-eye
=========

eagle-eye is a visualization tool which can generate an architecture diagram from terraform files.
 
The tool can be used locally or in a CI/CD pipeline to generate a diagram of your cloud infrastructure.

## 🚧 Project Status: Alpha Phase 🚧

Please be aware that our product is currently in **Alpha phase** . This means that while the core features have been implemented, 
the software is still undergoing significant testing and improvements.

**For now, we only support AWS Terraform provider**

## We Need Your Help!
🌟 **Your feedback is invaluable to us!** 🌟

As early adopters, your experiences, suggestions, and feedback are crucial in shaping the future of this project.
 
We would love to hear about your thoughts on what we're doing right, what we could do better, and any bugs you might have encountered.

### Join Our Community on Discord
To make it easier for you to share your feedback and for us to communicate with our users directly, we encourage you to join our **Discord server**.

It is a friendly space where you can:
- Report bugs 🐛
- Suggest new features or improvements ✨
- Stay updated with the latest project news 📢
- Connect with other community members and our development team 💬

**[Join Our Discord Server ➜](https://discord.gg/Rn6xgQUZsb)**

Thank you for supporting our project. Your involvement is key to the successful development of a product that meets and exceeds community expectations. Let's build something amazing together!

## How it works

The diagram generation is executed in 2 steps:
* eagle-eye CLI parses your Terraform code from a local directory and generates a JSON file with the parsed data.
* The JSON file is then sent to the Eagle Eye API, which generates a diagram file in PNG format.

No sensitive information is sent to the API, only Terraform blocks information is gathered.
 
In order to communicate with the Eagle Eye API, you need to create an account and generate API keys on [eagle-eye.io](https://eagle-eye.io).

## Installation & configuration

Download the CLI binary for your platform from the [releases page](https://github.com/brainboard/eagle-eye/releases)

Once downloaded, you just need to configure your API key generated from eagle-eye website: 

```bash
eagle-eye configure
```

## Usage 

The CLI requires exactly one argument, which is the path to your Terraform source code directory containiing .tf files.
 
eagle-eye only parses .tf and .tfvars files, not Terraform plan output or tfstate files.


### Generate diagram
```bash
eagle-eye /path/to/my-tf-project
```

### Generate a diagram with no connectors
```bash
eagle-eye /path/to/my-tf-project --hide-connectors
```

### Generate a diagram excluding specific resources using regular expression
```bash
eagle-eye /path/to/my-tf-project --exclude-types "aws_iam*|aws_eks_addon"
```


