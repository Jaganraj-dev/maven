pipeline{
    agent{
        any
    }
    stages{
        stage("git checkout"){
            steps{
                git(url: 'https://github.com/Jaganraj-dev/maven.git')
                echo "-----Start checkout execution----"
            }
            post{
                always{
                    echo "---always - checkout---"
                }
                success{
                    echo "---post success checkout---"
                }
                failure{
                    echo "---post failed checkout---"
                }
            }
        }
        stage("maven compile checkout"){
            steps{
                sh 'mvn clean compile'
                echo "-----maven clean compile----"
            }
        }
        stage("maven test checkout"){
            steps{
                sh 'mvn test'
                echo "-----run maven test----"
            }
        }
    }
    post{
        always{
            build job: 'MyMavenProject', wait: false
            echo "---pipeline - always---"
        }
        success{
            echo "---post success pipeline---"
        }
        failure{
            echo "---post failed pipeline---"
        }
}
