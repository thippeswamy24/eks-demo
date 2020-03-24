pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'sudo rm -rf /home/ec2-user/newfolder'
                sh 'sudo rm -rf *;sudo git clone https://github.com/thippeswamy24/eks-demo.git /home/ec2-user/newfolder'
            }
        }
       // stage('tfsvars create') {
         //   steps {
            //    sh 'sudo cp -rf /home/ec2-user/vars.tf /home/ec2-user/newfolder'
          //  }
      //  }
        stage('terraform init') {
            steps {
                sh 'sudo /home/ec2-user/terraform init /home/ec2-user/newfolder'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'sudo ls /home/ec2-user/newfolder; sudo /home/ec2-user/terraform plan /home/ec2-user/newfolder'
            }
        }
        stage('terraform apply') {
            steps {
                sh 'sudo /home/ec2-user/terraform apply --auto-approve /home/ec2-user/newfolder'
            }
        }
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

        
    }
}
