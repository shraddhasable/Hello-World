node {
    	stage('Build /Development') {
        
            echo 'I only execute on the master branch'	    
	    dir('D:\\Jenkins\\workspace\\JenkinsWar') {
            bat label: '', script: 'mvn compile'

		}
        
        }
		
   	stage('Pre-Production') {
        
            echo 'I only execute on the master branch'
            dir('D:\\Jenkins\\workspace\\JenkinsWar') {
            bat label: '', script: 'mvn package'

		}


        
        }
	stage('Testing') {
        
            echo 'I only execute on the master branch'
            dir('D:\\Jenkins\\workspace\\JenkinsWar') {
            bat label: '', script: 'mvn test'

		}

        
        }
	stage('Production') {
        
            input 'Deployment To Server '
            bat label: '', script: '''copy D:\\Jenkins\\workspace\\JenkinsWar\\target\\JenkinsWar.war  D:\\apache-tomcat-8.5.12\\webapps'''

        
        }
    
}
