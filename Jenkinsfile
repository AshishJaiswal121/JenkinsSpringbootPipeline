
pipeline {
agent any

tools{
maven "null"
}

stages {

stage("Checkout code"){
steps
{
checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '4aae679c-e398-4fb1-a0ee-0b88dc2d58db', url: 'https://github.com/AshishJaiswal121']]])
echo 'Check Out'
}
}
stage('Clean') {
steps {
bat 'mvn -f main/pom.xml clean'
echo 'Cleaning..'
}
}
stage('Compile') {
steps {
bat 'mvn -f main/pom.xml compile'
echo 'Compiling..'
}
}
stage('Test') {
steps {
bat 'mvn -f main/pom.xml test'
echo 'Testing..'
}
}
stage('Packaging') {
steps {
bat 'mvn -f main/pom.xml package'
echo 'Packageing..'
}
}
stage('Install') {
steps {
bat 'mvn -f main/pom.xml install'
echo 'Installing..'
}
}


}
}
