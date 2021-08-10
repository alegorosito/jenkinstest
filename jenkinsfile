pipeline {
    options {
        disableConcurrentBuilds()
    }
    
    agent any

    stages {
        
        stage('Build') {
            
            steps {
                echo "first step..."
                sleep 3
                echo "second step..."
            }
        }
        
    }
    
    post {
            always {
                influxDbPublisher(selectedTarget: 'influxdb', customData: assignURL("pedrito2"))
            }
        }

}

def assignURL(build_url) {
    def buildURL = [:]
    buildURL['url'] = build_url
    return buildURL
}