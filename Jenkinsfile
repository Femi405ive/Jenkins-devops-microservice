pipeline {
	agent any 
		stages('build') {
			steps{
				echo"build"
			}
		}
	    stages ("test") {
					steps{
				echo "test"
			}
		}

	    stages("integration test") {
			steps{
				echo "integration test"
			}
		}
	}