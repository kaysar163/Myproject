pipeline{
    agent any 
    parameters{
        string(name:'SPEC',defualtValue:"cypress/integration/**/**",description:"Enter the script path that you want to execute")
        choice(name:'BROWSER',choice['chrome','edge','firefox'],description:"choise the browser where you want to exeute your scripts")

    }
    options{
        ansIColor('xterm')
    }
    stages{
        stage('Bulding'){
            echo"Building the application"
        }
        stage('Testing'){
            steps{
                bat"npn i"
                bat"npx cypress run --browser=${BROWSER} --spec ${SPEC}"
                }
            }
            stage('Deploying'){
                echo "Deploy the application"
            }
        }
        post{
            alwaysg{
                it 'https://github.com/kaysar163/Cypress-demo-Framework'
            }
        }
    }
    