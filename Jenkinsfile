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
            }
        }
        stage('Cleaning up') { 
            steps { 
                echo "cleaning up"
                echo "rm -rf *"
                echo "rm -rf .git/"
            } 
        }
        stage('Verifying Cleanup') { 
            steps { 
                echo "verifying cleanup"
                sh "du -sh"
            } 
        }
    }
}
