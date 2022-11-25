pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  stages {

    stage('check ansible') {

      steps {
        
        sh '''

          cd ansible
          ls -lrt
          pwd
          chmod 400 devopskey.pem
          ls -lrt
          echo ${BRANCH_NAME}
          ansible-playbook -i hosts site.yaml -e "@group_vars/prod.yaml" -e "imagename=nginx:1.23" -e "target=dev"

        '''

      }

    }

    
  }

}
