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
