pipeline {
    agent any
	environment {
		env_list = "pflqa48"
		is_projmast_required = "no"
		version_nbr = "18.5.3"
		run_mode = "regression"
		scheduler = "airflow"
		chat_space = "Test"
		chat_update_interval_in_secs = "600"
		spl_note = "18.5.3_Regression"
	
	}
    stages {
	stage ('Test Stage') {

            steps {
                echo "Test Steps"
                echo "Jenkins URL: ${env.JENKINS_URL}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Node Name: ${env.NODE_NAME}"
                echo "Build ID: ${env.BUILD_ID}"
                echo "Build #: ${env.BUILD_NUMBER}"
                echo 'Build Version and Name: $params.CASE_BUILD_VERSION_AND_NAME'
            }
        }
        stage('Source Code Checkout') {
            steps {
                echo "......Finished checking out the code.........."
		sh ''' 
			echo "testing shell script"
			sh jen.sh ${name}
			a=10
			b=20

			#Check whether they are equal
			echo "checking name value below in if else"
			if [ ${name} == $b ]
			then
			    echo "a is equal to b"
			fi

			#Check whether they are not equal
			if [ $a != $b ]
			then
			    echo "a is not equal to b"
			fi
		
		'''

            }
        }
	stage('test3') {
	    steps {
		script {
		    if (env.JOB_NAME == 'jenshel') {
			echo 'exueint deploy'
		    } else {
			echo 'I execute elsewhere'
		    }
		}
	    }
	}
        stage('Script configuration') {
            steps {
                echo 'Hello, '
		echo "${env.is_projmast_required}"
		    echo "---------"
				sh """
				if [ "no" = "yes" ]; then
				  pwd
				else
				  pwd
                                  echo "${env.is_projmast_required}"
				fi
			"""
            }
        }
    }
}
