pipeline {
    agent any
    parameters {
        choice(name: 'UBUNTU', choices: ['18.10', '19.04'], description: 'Chose Ubuntu Release')
               }
    stages {
        stage('build') {
            input {
                    message "proceed?"
                    ok "yes"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Eric', description: 'name')
                    }
                }
     
            steps {
                 echo "Running ${env.BUILD_ID} ， ${env.BRANCH_NAME}on ${env.JENKINS_URL}"
                sh 'echo "Hello ${PERSON}, nice to meet you on ${UBUNTU}"'
                sh 'chmod +x app.sh'
                sh label: '', script: './app.sh'
            }
        }
    }
}
