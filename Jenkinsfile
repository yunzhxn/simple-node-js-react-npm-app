pipeline {
	agent any
    tools {
        nodejs 'nodejs' 
    }
	stages {
    	stage('Build') {
        	steps {
            	nodejs('nodejs'){
                		sh 'npm install'
            	}
        	}
    	}
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

        // stage('Dependency'){
        //     steps{
        //             withCredentials([string(credentialsId: 'NVD-API-KEY', variable: 'NVD_API_KEY')]) {
        //                 dependencyCheck additionalArguments: """
        //                     -o './'
        //                     -s './'
        //                     -f 'XML'
        //                     --prettyPrint
        //                     --nvdApiKey \${NVD_API_KEY}
        //                 """, odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
        //             }
        //           archiveArtifacts artifacts: 'dependency-check-report.xml', allowEmptyArchive: false
        //         dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
        //     }
        // }
	}
}
