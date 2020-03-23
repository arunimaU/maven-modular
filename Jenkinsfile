pipeline {
   agent any
	options {
             skipDefaultCheckout true
	}
       stages {
      stage('Git Checkout') {
         steps {
           git 'https://github.com/arunimaU/maven-modular.git'
		}
	}
	stage ('Build')
	   
	    {steps{
                sh '/opt/maven/bin/mvn clean package -Dmaven.test.skip=true'
	    }    }
      
     stage ('Release') 
     
     {steps{
	        sh '/opt/maven/bin/mvn --batch-mode release:clean release:prepare release:perform -DreleaseVersion-4.0 -DmasterVersion-1.2-SNAPSHOT'
          }
          }
       }}
