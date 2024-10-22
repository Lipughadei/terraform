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
        sh '''
        terraform init
        terraform apply
        '''
      }
    }
  }
}
