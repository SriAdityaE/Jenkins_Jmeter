# 🧪 Jenkins + JMeter Performance Testing Integration

This repository demonstrates how to integrate Apache JMeter with Jenkins to automate performance testing and visualize the results using the **Jenkins Performance Plugin**.

It showcases a basic yet powerful pipeline where Jenkins:
- Pulls the JMeter test script from GitHub
- Executes the test in non-GUI mode
- Collects the results in `.jtl` format
- Plots response times, throughput, and error trends using Jenkins plugins

## 📦 Project Structure

Jenkins_Jmeter/
├── sample_test_plan.jmx # Sample JMeter test plan (HTTP-based)
├── README.md # Project documentation

## ⚙️ Tools & Technologies

| Tool                     | Purpose                                  |
|--------------------------|-------------------------------------------|
| Apache JMeter            | Load/performance testing tool             |
| Jenkins                  | CI/CD pipeline and automation             |
| Jenkins Git Plugin       | Pulls this GitHub repo                    |
| Jenkins Performance Plugin | Visualizes JMeter test metrics         |
| GitHub                   | Stores version-controlled test assets     |



## 🚀 Jenkins Job Configuration

### 1️⃣ Prerequisites
- Jenkins installed and running
- Apache JMeter installed on the Jenkins machine and added to the PATH
- Plugins:
  - Git Plugin
  - Performance Plugin


### 2️⃣ Jenkins Job Setup (Freestyle)

#### 🔹 Source Code Management
- Choose **Git**
- Repository URL: `https://github.com/SriAdityaE/Jenkins_Jmeter.git`
- Add credentials if your repo is private (via **Secret Text** GitHub token)

#### 🔹 Build Step – Run JMeter
Add a **"Execute shell"** or **"Execute Windows batch command"** step:
```bash
jmeter -n -t sample_test_plan.jmx -l result.jtl


 Post-build Action – Publish Results
Select "Publish Performance Test Result Report"

Add:

Source data files: result.jtl

Performance report mode: JMeter

Jenkins will:

Plot graphs for response time, throughput, error %, etc.

Show performance trend history across builds


---

### 🟦 6. Sample Metrics

```markdown
## 📊 Sample Result Metrics Tracked

- Average Response Time
- 90th/95th Percentile
- Errors (count & %)
- Transactions Per Second (TPS)
- Graphs over time (build history)

## 🔐 Secure GitHub Integration

1. Generate a [GitHub Personal Access Token (classic)](https://github.com/settings/tokens)
2. In Jenkins:  
   `Manage Jenkins → Credentials → Global → Add Credentials → Secret Text`
3. Use these credentials in the Jenkins Git plugin setup

## 📄 .gitignore Recommendation

To keep your repo clean:

*.jtl
.log
/reports/
/.idea/
/.bak

## ✅ Future Enhancements

- Add parameterization using `.csv` for data-driven testing
- Archive `.jtl` as a Jenkins artifact
- Add Slack/email notifications for test results
- Use `HTML Publisher Plugin` for JMeter HTML reports (optional)
- Extend to GitHub Actions or Jenkins Pipeline

## 🙌 Contribution & Feedback

This is a demo repo to showcase CI/CD performance testing using JMeter.  
If you'd like to extend it with more scenarios (e.g., database testing, login flows), feel free to fork or raise a PR!

## 🧠 Author

**Sri Aditya**  
Performance Engineer | CI/CD Practitioner  
📌 [LinkedIn](https://www.linkedin.com/in/sriperf) 
