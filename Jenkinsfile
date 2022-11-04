pipeline {
agent any
tools{
maven 'Maven'
}

stages {
stage('git code') {
steps {
git credentialsId: 'git_creditials', url:'https://github.com/ravdy/hello-world.git'
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
deploy adapters: [tomcat9(credentialsId: '72d7ee54-4a8f-4d13-b30f-0a8445ab4a38', path: '', url: 'http://35.78.176.36:8081/')], contextPath: null, war: '**/*.war'
}
}

}
}
