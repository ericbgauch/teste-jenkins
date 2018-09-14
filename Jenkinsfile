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
                echo 'HOMOLOG --'
                withCredentials([string(credentialsId: 'HOTSITES_HOMOLOG_DB_HOST', variable: 'DB_HOST')]) {
                    sh 'echo $DB_HOST'
                }
                // echo credentials('HOTSITES_HOMOLOG_DB_HOST')
                // echo credentials('CHORAAPP_DB_NAME')
                // echo credentials('HOTSITES_HOMOLOG_DB_USER')
                // echo credentials('CHORAAPP_DB_PASS')

                // echo 'PROD --'
                // echo credentials('HOTSITES_PROD_DB_HOST')
                // echo credentials('CHORAAPP_DB_NAME')
                // echo credentials('HOTSITES_PROD_DB_USER')
                // echo credentials('CHORAAPP_DB_PASS')
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
