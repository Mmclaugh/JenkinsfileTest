pipeline{
    stages{
        stage('first'){
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches: scm.branches,
                    extensions: scm.extensions + [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory']],
                    userRemoteConfigs: scm.userRemoteConfigs
                ])
                
                sh 'ls -l'
            }
        }
    }
}
