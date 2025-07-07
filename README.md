# Jenkins + JMeter Integration

This repository demonstrates how to run Apache JMeter performance tests automatically through Jenkins, using GitHub as the source control system.

## 🔧 Tools Used

- **Apache JMeter** – for performance testing
- **Jenkins** – to automate the execution of JMeter scripts
- **GitHub** – to store and manage test scripts

## 📂 Repository Structure

Jenkins_Jmeter/
├── Jenkins_Jmeter.jmx # Jmeter Script with Simple transactions 
├── README.md # Project documentation (this file)



## 🚀 Jenkins Setup Steps

1. **Create a Jenkins Freestyle Job** (or Pipeline if preferred).
2. **Configure GitHub Integration**:
   - Add your GitHub Personal Access Token in Jenkins under **Manage Jenkins → Credentials → Global → Add Credentials**.
   - Use these credentials in the Jenkins job's Git plugin section.
3. **Pull the code from this repository** in the Jenkins job.
4. **Add a build step** to run the JMeter test:
   ```bash
   jmeter -n -t sample_test_plan.jmx -l result.jtl
