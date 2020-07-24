pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!' 
                checkout([$class: 'GitSCM', 
                    branches: [[name: env.GIT_TAG]],
                    extensions: [
                        [$class: 'SparseCheckoutPaths',  sparseCheckoutPaths:[[$class:'SparseCheckoutPath', path:'config']]],
                        [$class: 'RelativeTargetDirectory', relativeTargetDir: 'packages']
                    ],
                    userRemoteConfigs: [[url: 'git@github.com:sicker/jenkinstest.git',
                                       credentialsId: 'sicker27github']]
                ])
            }
        }
    }
}

