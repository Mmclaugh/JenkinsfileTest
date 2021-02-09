pipeline{
    agent any
    stages{
        stage('first'){
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches: scm.branches,
                    extensions: scm.extensions + [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory']],
                    userRemoteConfigs: scm.userRemoteConfigs
                ])
                
                sh 'ls -la'
                sh 'ls -la'
                
                sh 'ls -la subdirectory/*'
            }
        }
    }
}
