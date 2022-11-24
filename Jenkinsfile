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
          chmod 400 demokey.pem
          ls -lrt
          echo ${BRANCH_NAME}
          ansible-playbook -i hosts site.yaml -e "target=dev"

        '''

      }

    }

    
  }

}
