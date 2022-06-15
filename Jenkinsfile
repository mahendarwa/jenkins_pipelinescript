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
        stage('Source Code Checkout') {
            steps {
                echo "......Finished checking out the code.........."

            }
        }
        stage('Script configuration') {
            steps {
                echo 'Hello, '
				sh '''


				if [[ ${env.is_projmast_required} = "yes" ]]; then
				  pwd
				else
				  pwd
                                  echo "else"
				fi
			'''
            }
        }
    }
}
