# Jenkins-Shared-Library
Reusable Jenkins Shared Library for managing common pipeline code, custom steps, and utilities across multiple projects. Helps reduce duplication, improve maintainability, and streamline CI/CD workflows with centralized and modular pipeline functions.
# Jenkins Shared Library

This repository contains a **Jenkins Shared Library** for reusable pipeline code, custom steps, and utilities. It helps reduce duplication, improve maintainability, and streamline CI/CD workflows across multiple projects.

## 📂 Structure

```
(vars/)        # Groovy scripts for global functions
(src/)         # Shared classes and utilities
(resources/)   # Templates and configuration files
```

## 🚀 Usage

1. Go to **Manage Jenkins → Configure System → Global Pipeline Libraries**.
2. Add this repo as a library with a chosen name (e.g., `my-shared-lib`).
3. In your project’s `Jenkinsfile`, import the library:

   ```groovy
   @Library('my-shared-lib') _
   ```

## 🛠 Example

### In `vars/hello.groovy`

```groovy
def call(String name = 'World') {
    echo "Hello, ${name} from Shared Library!"
}
```

### In a `Jenkinsfile`

```groovy
@Library('my-shared-lib') _
pipeline {
    agent any
    stages {
        stage('Demo') {
            steps {
                hello('Vikash')
            }
        }
    }
}
```

## ✅ Benefits

* Centralized pipeline logic
* Reusable steps and functions
* Easier maintenance across projects
* Clean, modular, and scalable CI/CD pipelines
