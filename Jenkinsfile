node{
    stage('SCM Checkout'){
        git 'https://github.com/MMuniraja/calcwebapp.git'
    }
    stage('Compile Package'){
        def mvnHome = tool name: 'MAVEN', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
    }
    stage('Deploy to Tomcat'){
        cp 'target/*.war /opt/tomcat9/webapps'
    }
    stage('Email Notification'){
      mail bcc:'', body:'''Hi Welcome to Jenkins Pipeline alerts
      Thanks
      M.Muniraja''', cc:'', from:'', replyTo:'', subject:'Jenkins Job', to:'mmuni1990@gmail.com'
    }
    
}
