node (label: 'jenkinsslave') {
   stage('SCM Git Checkout'){
    // Clone repo
        git 'https://github.com/pranavdh/mavendemo-webapp'
   }
   stage('Compile Package'){
        def mvnHome = tool name: 'GitHubJenkinsMavenWebApp01', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        //sh 'mvn package'
         }
   stage('Deploy WAR file to AWS EC2 Prep'){
          sshagent(['tomcat-SSH-WAR-Files-AWSEC2s']) {
          sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@10.0.6.184:/opt/apache-tomcat-7.0.99/webapps'
          }
        }


   }
