pipeline {
<<<<<<< HEAD
    agent production-agent
=======
    agent { label 'production-agent' }
>>>>>>> origin/master

    stages {
        stage('system-update') {
            steps {
<<<<<<< HEAD
                apt update
=======
                echo "updating system"
                sh 'apt update'
>>>>>>> origin/master
            }
        }
        stage('restart-docker') {
            steps {
<<<<<<< HEAD
                systemctl restart docker
=======
                echo "restarting docker"
                sh 'systemctl restart docker'
>>>>>>> origin/master
            }
        }
        stage('remove-stack') {
            steps {
<<<<<<< HEAD
                docker stack rm voosool-stack
=======
                echo "removing old voosool-stack"
                sh 'docker stack rm voosool-stack'
>>>>>>> origin/master
            }
        }
        stage('build') {
            steps {
<<<<<<< HEAD
                docker-compose -f production.yml up --build -d
=======
                echo "building code"
                sh 'docker-compose -f production.yml up --build -d'
>>>>>>> origin/master
            }
        }
        stage('deploy') {
            steps {
<<<<<<< HEAD
                docker stack deploy -c production.yml voosool-stack
            }
        }
    }
}
=======
                echo "deploying code"
                sh 'docker stack deploy -c production.yml voosool-stack'
            }
        }
    }
    post {
        success{
            slackSend channel: 'alert-manager', color: 'good', message: "BUILD SUCCESSFULL!!!\nBUILD='${env.JOB_NAME}'\nbranch='${env.BRANCH_NAME}'\ntarget-branch='${env.CHANGE_TARGET}'\nbuild-number='#${env.BUILD_NUMBER}'\nbuild-id='#${env.BUILD_ID}\ntimestamp='${env.TAG_TIMESTAMP}'\nbuild-url='${env.BUILD_URL}'\ntime='${currentBuild.startTimeInMillis}ms'\nduration-for-build='${currentBuild.duration}ms'", teamDomain: 'voosool', tokenCredentialId: 'slack-channel'
        }
        failure{
            slackSend channel: 'alert-manager', color: 'danger', message: "BUILD FAILED WARNING!!!\nBUILD='${env.JOB_NAME}'\nbranch='${env.BRANCH_NAME}'\ntarget-branch='${env.CHANGE_TARGET}'\nbuild-number='#${env.BUILD_NUMBER}'\nbuild-id='#${env.BUILD_ID}\ntimestamp='${env.TAG_TIMESTAMP}'\nbuild-url='${env.BUILD_URL}'\ntime='${currentBuild.startTimeInMillis}'\nduration-for-build='${currentBuild.duration}ms'", teamDomain: 'voosool', tokenCredentialId: 'slack-channel'
        }
    }
}
>>>>>>> origin/master
