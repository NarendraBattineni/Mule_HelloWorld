pipeline{
 agent any
 environment {
    ANYPOINT = credentials('ANYPOINT')
 }
 tools {
       maven 'maven'
       jdk 'jdk'
 }
 stages {
 	stage ('Build'){
 		steps {
 			     bat 'mvn clean install'
 			     echo 'Build Complete'
 		}
 	}
 	stage ('Deploy'){
 		steps {
        bat 'cd target & move *.jar D:/Srivis-Mule-Training/mule-enterprise-standalone-4.2.1/apps'
 			    }
 		 }
 	}
 post {
    always {
        emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
    }
}
}
