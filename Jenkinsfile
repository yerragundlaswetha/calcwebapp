node{
    stage('SCM Checkout'){
        git 'https://github.com/MMuniraja/calcwebapp.git'
    }
    stage('Compile Package'){
        def mvnHome = tool name: 'M3', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('Deploy to Tomcat'){ 
        sh 'cp target/*.war /opt/tomcat9/webapps'
    }
    stage('Email Notification'){
      mailx bcc:'', body:'''Hi Welcome to Jenkins Pipeline alerts
      Thanks
      M.Muniraja''', cc:'', from:'', replyTo:'', subject:'Jenkins Job Status', to:'mmuni1990@gmail.com'
    }
    
}
