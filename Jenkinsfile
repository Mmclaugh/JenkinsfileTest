pipeline{
    stages{
        stage('Selecte an Account') { 
            steps { 
                script { 
                env.ACCOUNTDATA = input message: 'Pick AWS Account', 
                parameters: [choice(name: 'ACCOUNTDATA', choices: AccountMap.toList(), description: 'AWS account name and number')] 
                env.ACCOUNTNAME = sh( script: '''\
                #!/bin/bash\
                echo "${env.ACCOUNTDATA}" | awk -F ":" '{print $1}'\
                ''', returnStdout: true) 
                env.ACCOUNTNUMBER = sh( script: '''\
                #!/bin/bash\
                echo "${env.ACCOUNTDATA}" | awk -F ":" '{print $2}'\
                ''', returnStdout: true) 
                } 
            } 
        }
    }
}
