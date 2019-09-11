node {
    	stage('Build /Development') {
        	fileExists 'properties.txt'
        	bat label: '', script: 'set /p Build=<properties.txt'
        	bat label: '', script: 'cd %Build%'
        	bat label: '', script: 'mvn compile'
		bat label: '', script: 'for /f "delims=" %%x in (D:/Jenkins/workspace/Hello-World-Pipeline/properties.txt) do set Build=%%x'

            
        }
       
        
        stage('Pre-Production') {       
            	bat label: '', script: 'mvn package'

	}
	stage('Testing') {        
        	bat label: '', script: 'mvn test'

        }
	stage('Production') {        
            	dir('target/'){
            		input 'Deploy to Production Server'
 		        bat label: '', script: 'copy "HelloWorld.war"  "D:/apache-tomcat-8.5.12/webapps"'
 
        	}
        
        }
    
}
