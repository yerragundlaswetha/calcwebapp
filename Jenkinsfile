node{
    stage('SCM Checkout'){
        git 'https://github.com/MMuniraja/calcwebapp.git'
    }
    stage('Compile Package'){
        def mvn_version = 'M3'
        def mvnHome = tool name: 'MAVEN_HOME', type: 'Maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('Deploy to Tomcat'){ 
        sh 'cp target/*.war /opt/tomcat9/webapps'
    }    
}
