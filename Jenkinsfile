pipeline {
   agent any
stages {
      stage('Git Checkout') {
         steps {
            git 'https://github.com/AmalaSuram/FoodZone.git'
}
}
stage('Build') {
steps {
sh '/opt/maven/bin/mvn clean verify package'
}
}
stage ('Deploy') {
steps {
sh '/opt/maven/bin/mvn clean deploy'
}
}
stage ('Release') {
steps {
sh 'export JENKINS_NODE_COOKIE=dontkillme ;nohup java -jar $WORKSPACE/target/*.jar &'
}
}
  }
}
