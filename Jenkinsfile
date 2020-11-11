node{
  stage('SCM Checkout'){
    git 'https://github.com/vidyasagarkolusu/my-app'
  }
  stage('Compile-Package'){
   // Get Maven home  path
    def mvnHome = tool name: 'mymaven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  
  stage('SonarQube Analysis') {
    def mvnHome = tool name: 'mymaven', type: 'maven'
    withSonarQubeEnv('sonar-6') {
      sh "${mvnHome}/bin/mvn  sonar:sonar"
    }
  }
  
  stage('Email Notification'){
    mail bcc: '', body: 'Welcome to Jenkins Job Alerts', cc: 'sagar.vidya921@gmail.com', from: '', replyTo: '', subject: 'Jenkins JOb', to: 'sagar.vidya279@gmail.com'
  }
 }
