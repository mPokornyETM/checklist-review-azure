
---

# 🧩 Checklist Review Azure DevOps Extension

---

An Azure DevOps extension that integrates markdown-based code review checklists into your pipelines. It ensures that code changes meet review standards before merging, using the Checklist Review CLI as the validation engine.

---

⚡️ **Supporting the Project**

> "Open source" does not mean "includes free support"

You can support the contributor and buy him a coffee.
[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/mpokornyetm)
Every second invested in an open-source project is a second you can't invest in your own family / friends / hobby.
That's the reason, why supporting the contributors is so important.

Thx very much for supporting us.

---

## ✨ Features

- Validate markdown checklists during Azure DevOps builds
- Block pull request completion if required checklist items are incomplete
- Customizable checklist location and rules
- Works with YAML pipelines and classic build definitions
- Lightweight and easy to integrate

---

## 📦 Requirements

- Azure DevOps organization/project
- Installed `checklist-review-cli`
- Checklist file (e.g. `.github/review-checklist.md`) in your repository

---

## 📋 Usage Examples

### ✅ YAML Pipeline

```yaml
steps:
- script: |
    checklist-review validate .github/review-checklist.md
  displayName: 'Validate Code Review Checklist'
```

### ✅ Classic Pipeline

1. Add a **Command Line Script** task
2. Use:

```bash
checklist-review validate .github/review-checklist.md
```

3. Configure the task to fail the build if validation fails

---

## ⚙️ Configuration

Add a `.checklist-review.yml` file to your repository root:

```yaml
checklist:
  path: .github/review-checklist.md
  required: true
  failBuildIfIncomplete: true
```

---

## 🛠 Development

To build and test the extension locally:

```bash
git clone https://github.com/mPokornyETM/checklist-review-azure
cd checklist-review-azure
npm install
```

Use the [Azure DevOps Extension SDK](https://github.com/microsoft/azure-devops-extension-sdk) and [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/devops/extension) to package and publish the extension.

---

## 📄 License

MIT License. See [LICENSE](./LICENSE) for details.

---

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

---

## 📬 Contact

Maintained by Martin Pokorný. For issues, use the GitHub issue tracker.

---

Would you like help generating the `vss-extension.json` manifest or packaging instructions for the Azure DevOps Marketplace?
