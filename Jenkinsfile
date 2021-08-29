pipeline {
    agent any
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }
    stages {
        stage ('Compile Stage') {

            steps {
                    //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                    sh 'mvn clean compile'
                }
            }

        stage ('Testing Stage') {

            steps {
                //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                    sh 'mvn test'
                }
            }
        


        stage ('Package Stage') {
            steps {
                //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                    sh 'mvn package'
                }
            }
        
        stage ('Deployment Stage') {
            steps {
                //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                    sh 'scp /var/lib/jenkins/workspace/pipeline-demo-job/gameoflife-web/target/gameoflife.war root@ip-172.31.44.1:/opt/tomcat/apache-tomcat-9.0.52/webapps'
                    sh 'mvn deploy'
            }
        }
    }
}
