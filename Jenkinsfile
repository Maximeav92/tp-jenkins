pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Etape 1 : Lancement du build...'
                bat 'echo "Bonjour depuis Windows !"'
            }
        }
        stage('Deploy (avec sécurité)') {
            steps {
                timeout(time: 3, unit: 'MINUTES') {
                    retry(3) {
                        bat 'echo "Simulation de déploiement en cours..."'
                    }
                }
            }
        }
        stage('Test (avec erreur volontaire)') {
            steps {
                bat 'echo "Oh non, une erreur !"; exit /b 1'
            }
        }
    }
    post {
        always {
            echo 'POST : Ceci s\'affiche TOUJOURS, peu importe le résultat.'
        }
        success {
            echo 'POST : Ceci s\'affiche uniquement si tout est VERT.'
        }
        failure {
            echo 'POST : Ceci s\'affiche uniquement s\'il y a un echec (ROUGE).'
        }
    }
}
