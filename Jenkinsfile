pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    def repoUrl = 'https://github.com/yourusername/yourrepo.git'
                    def branch = 'main'
                    def repoDir = 'yourrepo'

                    // Clone the repository
                    sh "rm -rf ${repoDir}" // Clean up any previous clone
                    sh "git clone -b ${branch} ${repoUrl} ${repoDir}"
                }
            }
        }

        stage('Run Groovy Script') {
            steps {
                script {
                    def repoDir = 'yourrepo'

                    // Change to the repository directory and execute the Groovy script
                    dir(repoDir) {
                        sh "groovy yourscript.groovy"
                    }
                }
            }
        }
    }

    post {
        always {
            // Clean up the workspace
            cleanWs()
        }
    }
}
