pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/abhiemizen/JenkinsProject.git'
            }
        }
        stage('Deploy') {
    steps {
        sshagent(credentials: ['jenkinsserverprivatekey']) {
            sh '''
                ssh -o StrictHostKeyChecking=no -p 2286 emizentechdev@14.99.153.8 '
                sudo git clone https://github.com/abhiemizen/JenkinsProject.git /var/www/domains/source
                '
            '''
           }
        }
      }

    }
}
