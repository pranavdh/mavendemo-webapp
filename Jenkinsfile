node {
   stage('SCM Git Checkout'){
    // Clone repo
        git 'https://github.com/pranavdh/mavendemo-webapp'
   }
   stage('Compile Package'){
        def mvnHome = tool name: 'GitHubJenkinsMavenWebApp01', type: 'maven'
        sh "${mvnHome}/bin/mvn package"
        //sh 'mvn package'
         }

   }
