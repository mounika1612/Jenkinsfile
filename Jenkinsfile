pipeline {
agent any
tools{
maven 'Maven'
}

stages {
stage('git code') {
steps {
 git branch: 'main',  url: 'https://github.com/mounika1612/Jenkinsfile.git'
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
deploy adapters: [tomcat9(credentialsId: 'admin', path: '', url: 'http://43.206.150.39:8081/')], contextPath: 'Jenkinsfile', war: '**/*.war'
}
}

}
}
