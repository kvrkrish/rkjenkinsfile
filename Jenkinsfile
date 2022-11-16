node {

    stage('git clone') {
	
	git branch: 'main', credentialsId: 'rkgit', url: 'https://github.com/kvrkrish/RK.git'
        
    }
	
    stage('clean') {
	
	bat 'mvn clean'
        
    }
    
    stage('validate') {
	
	bat 'mvn validate'
        
    }
	stage ('sonar scan'){
	bat 'mvn sonar:sonar -Dsonar.host.url=http://13.232.70.0:9000 -Dsonar.login=31c6b4704868b6ee29767b198f41a0c768cbba8e'
	}
	
    stage('compile') {
    bat 'mvn compile'  
    }
	stage('test') {
    bat 'mvn test'  
    }
	stage('package') {
    bat 'mvn package'  
    }
	stage('deploy') {
    bat 'mvn deploy'  
    }
	
}

