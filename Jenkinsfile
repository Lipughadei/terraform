pipeline{
  agent {
    label 'agent-T'
  }
  stages {
    stage('git checkout'){
      steps{
          git 'https://github.com/Lipughadei/Terraform_EC2_instance_creation.git'
      }
    }
    stage('terraform') {
      steps{
        script{
          sh "terraform init"
           withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-cred', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]){
              sh 'AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID" AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"  terraform apply'
           }
        }
      }
    }
  }
}
