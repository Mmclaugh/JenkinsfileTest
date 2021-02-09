pipeline{
    agent any
    stages{
        stage ('Checkout'){
            steps{
                echo "git branch: 'master', url: 'https://github.com/Mmclaugh/JenkinsfileTest.git'"
            }
        }
        stage('Selecte an Account') { 
            steps { 
                echo "This is a second PR"
                echo "this is a test"
                echo "this should trigger a webhook build"
                echo "this time only the push should be sent"
            } 
        }
        stage('A second stage') { 
            steps { 
                echo "this is a test"
                echo "Adding a second output"
                echo "This is a new edit on the PR"
                echo "test"
                echo "test"
            } 
        }
    }
}
