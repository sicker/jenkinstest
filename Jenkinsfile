pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'dev/1.0.0.0']],
                    extensions: [
                        [$class: 'SparseCheckoutPaths',  sparseCheckoutPaths:[[$class:'SparseCheckoutPath', path:'config']]]
                    ],
                    userRemoteConfigs: [[url: 'git@github.com:sicker/jenkinstest.git',
                                       credentialsId: 'sicker27GitHub']]
                ])
            }
        }
    }
}

