pipeline{
    agent any
    stages{
        stage ('Checkout'){
            steps{
                sh "du -sh"
                echo "git branch: 'master', url: 'https://github.com/Mmclaugh/JenkinsfileTest.git'"
                checkout scm
                sh "pwd"
                sh "ls -la"
                sh "du -sh"
                echo "cleaning up"
                sh "rm -rf *"
                sh "rm -rf .git/"
                echo "verifying cleanup"
                sh "du -sh"
            }
        }
        stage('Selecte an Account') { 
            steps { 
                echo "This is a second PR"
                echo "this is a test"
                echo "this should trigger a webhook build"
                echo "this time only the push should be sent2"
            } 
        }
        stage('A second stage') { 
            steps { 
                echo "this is a test213"
                echo "test"
            } 
        }
    }
}
