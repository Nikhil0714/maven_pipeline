pipeline {
    agent any
    stages {
        stage('Gitclone') {
            steps {
                git 'https://github.com/VinCloud1/hello-world-master.git'
                echo 'cloning the project...'
                // commands to build the project
            }
        }
        stage('Build') {
            steps {
                sh 'yum install maven -y'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
                echo 'Build the project...'
                // commands to run tests
            }
        }
        stage('Tomcatserverdeploy ') {
            steps {
                echo 'Deploying to Tomcatserver...'
                deploy adapters: [tomcat8(credentialsId: 'Tomcat_8.0_login', path: '', url: 'http://13.215.201.72:8080/')], contextPath: null, war: '**/*.war'
                // commands to deploy to production
            }
        }
        stage('Monitor') {
            steps {
                echo 'Monitoring the production environment...'
                // commands to monitor the production environment
            }
        }
        stage('UAT_1') {
            steps {
                echo 'Monitoring the production environment...'
                // commands to monitor the production environment
            }
        }
        stage('UAT_2') {
            steps {
                echo 'Monitoring the production environment...'
                // commands to monitor the production environment
            }
        }        
    }
}
