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
                stage('Test On Linux') {
                    agent {
                        docker { 
                        image 'nginx'
                        }
                    }
                    steps {
                        sh 'echo "This is ubuntu image"'
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
