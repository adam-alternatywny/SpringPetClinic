pipeline{
    agent{label:'master'}
    tools{maven:'default'}
    stages{
        stage('Checkout'){
            steps{
                git branch:'main', url:'https://github.com/adam-alternatywny/SpringPetClinic.git'
            }
        }    
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
