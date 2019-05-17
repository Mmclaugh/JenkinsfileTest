pipeline{
    stages{
        stage('first'){
            steps{
                variable="testing"

                echo '''This is a string that i am ${variable}'''
                echo """This is a string that i am ${variable}"""

                sh ''' echo "This is a string that will not print out the ${variable}" '''

                sh ''' export variable='correctly'
                echo "This is a string that will evaulate ${variable}" '''

                variable="correctly"
                sh """ echo "This is a string that will evaulate ${variable}" """
            }
        }
    }
}
