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
           stage('deploy') {
             steps {
               sh "sudo cp target/*.war /opt/apache-tomcat-10.1.35/webapps/"
             }
           }
         }
}
