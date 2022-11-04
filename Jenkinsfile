pipeline {
agent any


stages {
stage('git code') {
steps {
 
echo 'getting source code'
}
}

stage('build code'){
steps{
sh 'mvn clean install package'
echo 'building'
}

}
stage('deploying to tomcat server'){
steps{
deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://52.192.188.175:8081/')], contextPath: 'Jenkinsfile', war: '**/*.war'
}
}

}
}
