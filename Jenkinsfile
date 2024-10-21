pipeline {
agent any
stages {
stage('Checkout')
{ steps {
git branch: 'main', url: 'https://github.com/prasannaG300618/sample_test.git'
}
}
stage('Build')
{ steps {
sh 'mvn clean package'
}
}
stage('Test')
{
steps {
sh 'mvn test'
}
}
// Add more stages as needed (e.g., Deploy, PublishArtifacts) 
}
post {
always
{
// Clean up or notify 
}
success {
// Notify 
success
}
failure {
// Notify
failure }
}
}
