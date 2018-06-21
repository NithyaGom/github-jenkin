pipeline {
    agent none
    stages {
        stage('Run Tests') {
            parallel {
                stage('Test On ubuntu') {
                    agent {
                        docker { 
                        image 'ubuntu' 
                        }
                    }
                    steps {
                        sh 'echo "This is ubuntu image"'
                    }
                    post {
                        success {
                            echo "parallel execution"
                        }
                    }
                }
                stage('Test On nginx') {
                    agent {
                        docker { 
                        image 'nginx'
                        }
                    }
                    steps {
                        sh 'echo "This is nginx image"'
                    }
                    post {
                        success {
                            echo "parallel execution succeeded"
                        }
                    }
                }
            }
        }
    }
}
