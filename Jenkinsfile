node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
    sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}

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
