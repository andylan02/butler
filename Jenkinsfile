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
                sh 'echo "Hello, BRANCH_NAME: %BRANCH_NAME%,%BUILD_ID%, %BUILD_NUMBER%, ${PERSON}, nice to meet you on ${UBUNTU}"'
                sh 'chmod +x app.sh'
                sh label: '', script: './app.sh'
            }
        }
    }
}
