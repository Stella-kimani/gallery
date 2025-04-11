pipeline{
    agent any

    tools {
        nodejs "nodejs" 
    }

    environment {
        EMAIL_RECIPIENT = 'stella.kimani@student.moringaschool.com'
        //RENDER_DEPLOY_HOOK = " "
		//SLACK_TOKEN = "  "
		//WEBSITE_URL = " "
    }


    stages{
        stage("Cloning repository"){
            steps{
                git branch:"master", url:"https://github.com/Stella-kimani/gallery.git"
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

       
	    //stage("Deploy to Render") {
            //steps {
                //echo 'Deploying application to Render...'
                //sh "curl -X POST ${RENDER_DEPLOY_HOOK}"
            //}
        //}

    }


    //post {
        //success {
            //echo 'Pipeline completed successfully!!'
			//slackSend botUser: true, 
			//channel: '#ip1', 
			//color: '#00ff00', 
			//message: "${currentBuild.number} ${WEBSITE_URL}", 
			//tokenCredentialId: "${SLACK_TOKEN}"
			
			
        //}
        //failure {
            //mail to: "${EMAIL_RECIPIENT}",
                 //subject: 'Pipeline Failure Notification',
                 //body: 'The pipeline failed at some stage. Please check Jenkins logs for details.'
        //}
        //always {
            //echo 'Pipeline execution complete!!'


        //}
        //aborted {
            //echo 'Pipeline execution aborted!!' 
        //}
    //}
    
}