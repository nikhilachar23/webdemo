@Library('java_pipeline_groovy@main') _

pipeline {
  agent any
         stages {
           stage('Checkout') {
             steps {
               //sh "rm -rf webdemo"
               //sh "git clone https://github.com/nikhilachar23/webdemo.git"
               checkoutcode()
             }
           }
           stage('build') {
             steps {
               sh "cd webdemo"
               //sh "mvn clean package"
               buildproject('hello-world')
             }
           }
           stage('publish') {
             steps {
               // sh "cd webdemo"
               sh "mvn clean deploy"
               // buildproject('hello-world')
             }
           }
           stage('download') {
             steps {
             }
           }
           stage('deploy') {
             steps {
              // sh "sudo cp target/*.war /opt/apache-tomcat-10.1.35/webapps/"
                sh "cp hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.35/webapps/"
             }
           }
         }
}
