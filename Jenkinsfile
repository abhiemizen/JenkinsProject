pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-user/your-repo.git'
            }
        }
        stage('Deploy') {
            steps {
                sshagent(credentials: ['jenkinsserverprivatekey']) {
                    sh '''
                        ssh -p 2286 emizentechdev@14.99.153.8 '
                        cd /var/www/domains/source && git clone https://github.com/abhiemizen/JenkinsProject.git 
                        '
                    '''
                }
            }
        }
    }
}
