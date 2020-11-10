node{
  stage('SCM Checkout'){
    git 'https://github.com/vidyasagarkolusu/my-app'
  }
  stage('Compile-Package'){
   // Get Maven home  path
    def mvnHome = tool name: 'mymaven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
    
   }
 }
