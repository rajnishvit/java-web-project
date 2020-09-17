pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("deploy") {
            steps {
                deploy adapters: [tomcat7(credentialsId: 'f3c88902-4535-478d-833c-a170a5ab9c31', 
                path: '', 
				url: 'http://ec2-13-127-126-145.ap-south-1.compute.amazonaws.com:8080/')], 
                contextPath: '/javawebproject', 
				war: '**/java-web-project.war'
            }
        }
    }
}
