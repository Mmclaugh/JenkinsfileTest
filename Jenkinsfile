pipeline{
    agent any
    stages{
        stage('Selecte an Account') { 
            steps { 
                script { 
                    input message: 'Pick AWS Account', 
                    parameters: [choice(name: 'ACCOUNTDATA', choices: ["yes", "no"], description: 'AWS account name and number')] 
                    sh( script: '''\
                    #!/bin/bash\
                    echo "${ACCOUNTDATA}" | awk -F ":" '{print $1}'\
                    ''', returnStdout: true) 
                    sh( script: '''\
                    #!/bin/bash\
                    echo "${ACCOUNTDATA}" | awk -F ":" '{print $2}'\
                    ''', returnStdout: true) 
                } 
            } 
        }
    }
}
