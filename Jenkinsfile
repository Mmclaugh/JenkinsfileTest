pipeline{
    agent any
    triggers {
        pollSCM '0 0 31 2 *'
    }
    stages{
        stage ('Checkout'){
            steps{
                echo "git branch: 'master', url: 'https://github.com/Mmclaugh/JenkinsfileTest.git'"
                checkout([$class: 'GitSCM',
                    branches : scm.branches,
                        userRemoteConfigs: scm.userRemoteConfigs,
                    extensions : scm.extensions + [
                        [$class: 'SubmoduleOption', disableSubmodules: false, parentCredentials: true, recursiveSubmodules: true, reference: '', trackingSubmodules: false],
                        [$class: 'CloneOption', noTags: false, depth: 0, reference: '', shallow: false],
                        [$class: 'GitLFSPull']
                        ],
                        gitTool: gitTool])
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
