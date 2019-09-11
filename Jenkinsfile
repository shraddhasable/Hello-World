node {
    	stage('Build /Development') {
        fileExists 'properties.txt'
        bat label: '', script: 'set /p Build=<properties.txt'
        bat label: '', script: 'cd %Build%'
        
        
        bat label: '', script: 'mvn package'
            
        }
        bat label: '', script: 'for /f "delims=" %%x in (D:/Jenkins/workspace/Hello-World-Pipeline/properties.txt) do set Build=%%x'
        dir('target/')
        {
            bat label: '', script: 'copy "HelloWorld.war"  "D:/apache-tomcat-8.5.12/webapps"'
 
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
