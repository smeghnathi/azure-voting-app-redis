pipeline {
    agent any
    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build'){
            steps{
                sh(script: 'ls')
                sh(script: 'docker images -a')
                sh(script: """
                    cd ..
                    cd azure-vote/
                    docker images -a
                    docker build -t jenkins-pipeline .
                    docker images -a                  
                """)
            }
        }
    }
}
