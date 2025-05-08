pipeline {
    agent {
    node {
        label 'AGENT-1'
    }
}
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    
    stages {
        stage("Build") {
            steps {
                echo "this block is for building"    
            }
        }
        stage("Test") {
            steps {
                echo "this block is for Testing"    
            }
        }
        stage("Deploy") {
            steps {
                echo "this block is for Deploy"    
            }
        }
        stage("check params"){
            steps{
                sh """
                    echo "Hello, ${params.PERSON}
                    echo "Biography, ${params.BIOGRAPHY}
                    
                """
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
        success {
            echo "pipeline is success"
        }
        failure {
            echo "pipeline is failed"
        }    
    }
 }
