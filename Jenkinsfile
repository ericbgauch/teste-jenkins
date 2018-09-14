pipeline {
    agent any
    stages{
        stage("Prepare") {
            steps {
                script{
                    if(env.GIT_BRANCH == 'origin/master'){
                        env.HOST = env.PROD_HOST
                    }else{
                        env.HOST = env.HOMOLOG_HOST
                    }
                }
            }
        }

        stage ("Create artifact") {
            steps {
		echo 'imprimir credential aqui'
            }
        }

    post {
        always {
            cleanWs()
        }
    }
}
