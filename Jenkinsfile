pipeline {
  agent any
  tools {
        nodejs "nodejs"
    }
    stages {
        stage('SCM checkout server') {
            steps {
		checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/arsh-ash/Portfolio-website.git']]])
		
		stash 'source'
            }
        }
	
        stage('next VM ') {
		agent { 
    		label 'jenkins-agent'
		}
            steps {
                unstash 'source'
                echo 'unstash successful'
            }
        }
        stage ('npm build server') {
            steps{
                unstash 'source'
                echo 'unstash is successfull'
                sh 'npm -v'
                echo 'node build successfull'
            }
        }
        stage ('manual test phase  UNDER CONSTRUCTION') {
            steps{
                unstash 'source'
                echo 'unstash is successfull'
                sh 'npm -v'
                echo 'node build perform here'
            }
        }
        stage ('docker-image phase for version control UNDER CONSTRUCTION') {
            steps{
                
                echo 'docker images build here'
                
                
            }
        }
    }
    
}
