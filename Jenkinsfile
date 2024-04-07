pipeline {
    agent any
    stages {
        stage("git checkout") {
            steps {
                script {
                    // Checkout the code from the Git repository
                    git url: 'https://github.com/Jaganraj-dev/maven.git'
                    echo "-----Start checkout execution----"
                }
            }
            post {
                always {
                    echo "---always - checkout---"
                }
                success {
                    echo "---post success checkout---"
                }
                failure {
                    echo "---post failed checkout---"
                }
            }
        }
        stage("maven compile checkout") {
            steps {
                script {
                    // Clean and compile the Maven project
                    sh 'mvn clean compile'
                    echo "-----maven clean compile----"
                }
            }
        }
        stage("maven test checkout") {
            steps {
                script {
                    // Run Maven tests
                    sh 'mvn test'
                    echo "-----run maven test----"
                }
            }
        }
    }
    post {
        always {
            // Trigger another Jenkins job as a post-build action
            build job: 'MyMavenProject', wait: false
            echo "---pipeline - always---"
        }
        success {
            echo "---post success pipeline---"
        }
        failure {
            echo "---post failed pipeline---"
        }
    }
}
