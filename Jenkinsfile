pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "badrekhan/devops-project1"
        TAG = "${BUILD_NUMBER}"
        GIT_REPO = "https://github.com/Badrekamil/k8s-manifests.git"
    }

    stages {

        stage('Clone GitOps Repo') {
            steps {
                git url: "${GIT_REPO}", branch: "main"
            }
        }

        stage('Update Deployment YAML') {
            steps {
                sh """
                sed -i 's|image:.*|image: ${DOCKER_IMAGE}:${TAG}|' deployment.yaml
                """
            }
        }

        stage('Commit & Push Changes') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'github-creds',
                    usernameVariable: 'GIT_USER',
                    passwordVariable: 'GIT_PASS'
                )]) {

                    sh """
                    git config user.name "jenkins"
                    git config user.email "jenkins@example.com"

                    git add deployment.yaml
                    git commit -m "Update image to ${TAG}"

                    git push https://${GIT_USER}:${GIT_PASS}@github.com/Badrekamil/k8s-manifests.git main
                    """
                }
            }
        }
    }
}
