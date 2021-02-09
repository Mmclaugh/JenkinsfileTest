pipeline{
    agent any
    stages{
        stage ('Checkout'){
            git branch: 'exampleBranch', url: 'https://github.com/Mmclaugh/JenkinsfileTest.git'
        }
        stage('Selecte an Account') { 
            steps { 
                echo "This is a second PR"
                echo "this is a test"
            } 
        }
        stage('A second stage') { 
            steps { 
                echo "this is a test"
                echo "Adding a second output"
            } 
        }
    }
}
