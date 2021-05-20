pipeline {
  agent {
    label 'NODEJS'
  }

  stages {
    stage ('Dependencies install') {
        steps {
        sh '''
        npm install
        '''
        }
    }

    stage('Prepare Artifacts') {
       steps {
       sh '''
         zip -r ../todo.zip *
       '''
       }
    }
    stage('Upload Artifacts') {
        steps {
            sh '''
            curl -v -u admin:Omkar@123 --upload-file /home/ubuntu/workspace/todo.zip http://172.31.4.7:8081/repository/todo/todo.zip
            '''
        }
    }
  }
}
