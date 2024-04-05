// node {
//   stage('SCM') {
//     checkout scm
//   }
//   stage('SonarQube Analysis') {
//     def scannerHome = tool 'SonarScanner';
//     withSonarQubeEnv() {
//     sh "${scannerHome}/bin/sonar-scanner"
//     }
//   }
// }

// pipeline {
//     agent any
    
//     stages {
//         stage('Check GitHub Connection') {
//             steps {
//                 script {
//                     try {
//                         // Run git ls-remote command to check GitHub connectivity
//                         sh "git ls-remote -h -- https://github.com/girishkumarv07/rust-demo.git HEAD"
                        
//                         // If the command succeeds, print a success message
//                         echo "Successfully connected to GitHub repository"
//                     } catch (Exception e) {
//                         // If the command fails, print an error message
//                         echo "Failed to connect to GitHub repository"
//                         error "Failed to connect to GitHub repository: ${e.message}"
//                     }
//                 }
//             }
//         }
//           stage('SonarQube Analysis') {
//     def scannerHome = tool 'SonarQube_Server';
//     withSonarQubeEnv() {
//       sh "${scannerHome}/bin/sonar-scanner"
//     }
//   }
//     }
// }


pipeline {
    agent any
    
    stages {
        stage('Check SonarQube Connection') {
            steps {
                script {
                    try {
                        // Replace 'http://localhost:9000' with the URL of your SonarQube server
                        def sonarqubeURL = 'http://localhost:9002/'
                        
                        // Try to connect to SonarQube server
                        sh "curl -s -o /dev/null $sonarqubeURL"
                        
                        // If the connection is successful, print a success message
                        echo "SonarQube is connected successfully"
                    } catch (Exception e) {
                        // If the connection fails, print an error message
                        echo "Failed to connect to SonarQube"
                        error "Failed to connect to SonarQube: ${e.message}"
                    }
                }
            }
        }
    }
}

