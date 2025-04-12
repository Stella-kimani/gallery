pipeline{
    agent any

    tools {
        nodejs "nodejs" 
    }

    environment {
        EMAIL_RECIPIENT = "stella.kimani@student.moringaschool.com"
        RENDER_DEPLOY_HOOK = "https://api.render.com/deploy/srv-cvt2e7q4d50c73dck2q0?key=kiY0iKaTdO4"
		//SLACK_TOKEN = ""
		WEBSITE_URL = "https://gallery-1-zlid.onrender.com/"
    }


    stages{
        stage("Cloning repository"){
            steps{
                git branch:"master", url:"https://github.com/Stella-kimani/gallery"
            }
        }

        stage("Install dependencies"){
            steps{
                sh "npm install"
            }
        }

        stage("Test code"){
            steps{
                sh "npm test"
            }
        }

       
	    stage("Deploy to Render") {
            steps {
                echo 'Deploying application to Render...'
                sh "curl -X POST ${RENDER_DEPLOY_HOOK}"
            }
        }

    }


    
    
}