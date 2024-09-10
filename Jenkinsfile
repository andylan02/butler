pipeline {
    agent any
    parameters {
        choice(name: 'UBUNTU', choices: ['18.10', '19.04'], description: 'Chose Ubuntu Release')
        string(name: 'STATEMENT', defaultValue: 'hello; ls /', description: 'What should I say?')
               }
    stages {
        stage('Example') {
              steps {
                /* CORRECT */
                sh('echo ${STATEMENT}')
              }
            }
        
        stage('build') {
            input {
                    message "proceed?"
                    ok "yes"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Eric', description: 'name')
                    }
                }
             
     
            steps {
                echo "Running BUILD_ID：${env.BUILD_ID}，BRANCH_NAME：${env.BRANCH_NAME} on ${env.JENKINS_URL}"
                echo "Running BUILD_NUMBER：${env.BUILD_NUMBER}，BUILD_TAG：${env.BUILD_TAG} on ${env.JENKINS_URL}"
                echo "Running EXECUTOR_NUMBER：${env.EXECUTOR_NUMBER}，JOB_NAME：${env.JOB_NAME} on ${env.JENKINS_URL}"
                echo "Running NODE_NAME：${env.NODE_NAME}，WORKSPACE：${env.WORKSPACE} on ${env.JENKINS_URL}"
                sh 'echo "Hello ${PERSON}, nice to meet you on ${UBUNTU}"'
                sh 'chmod +x app.sh'
                sh label: '', script: './app.sh'
            }
        }
    }
}
