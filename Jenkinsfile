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
        // Download and install Terraform CLI
        bat 'curl -LO https://releases.hashicorp.com/terraform/1.0.11/terraform_1.0.11_windows_amd64.zip'
        bat 'Expand-Archive terraform_1.0.11_windows_amd64.zip -DestinationPath $env:ProgramFiles/terraform'
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
