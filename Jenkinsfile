pipeline {
    agent any
    environment {
        PY_EXE = "C:\\prjtools\\python\\ver_3.7.6_p14\\python.exe"
    }
    parameters {
        string(name: 'PYTHON_FILE_PATH', defaultValue: '', description: 'Enter the path to the Python file')
    }
    stages {
        stage('Validate files') {
            steps {
                script {
                    def file_path = params.PYTHON_FILE_PATH.trim()
                     else {
                        def file = new File(file_path)
                        if (!file.exists()) {
                            error('File does not exist')
                        } else {
                            echo "File exists at ${file_path}"
                        }
                    }
                }
            }
        }
        stage('Read and Write Python File') {
            steps {
                script {
                    def output = bat(script: "${PY_EXE} ${PYTHON_FILE_PATH}", returnStdout: true).trim()
                    writeFile file: 'output2.txt', text: output
                }
            }
            post {
                always {
                    bat "copy output2.txt C:\\zzzz"
                }
            }
        }
    }
}
}
