pipeline {
    agent any
    stages {
        stage('version') {
            steps {
                bat "python --version"
            }
        }
        stage('hello'){
            steps{
                bat '"C:/python/python.exe" C:/zzzz/hello.py"'
            }
        }
    }
}
