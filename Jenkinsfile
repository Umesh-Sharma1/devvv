pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'echo "Building the code"'
      }
    }
    stage('Test') {
      steps {
        bat 'echo "Running the tests"'
      }
    }
    stage('Deploy') {
     steps {
        // Download and install 7-zip
        bat 'curl -L https://www.7-zip.org/a/7z1900-x64.exe -o 7z.exe'
        bat '7z.exe x terraform_1.0.11_windows_amd64.zip -o"$env:ProgramFiles\\terraform"'
        bat 'setx path "$env:path;C:/Program Files/terraform" /M'

        // Initialize Terraform configuration
        bat 'terraform init'

        // Plan Terraform deployment
        bat 'terraform plan -out=plan.tfplan'

        // Apply Terraform deployment
        bat 'terraform apply -auto-approve plan.tfplan'
     }
    }
  }
}
