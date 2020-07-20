pipeline{
    agent any
        stages{
            stage('Git Checkout'){
                    steps{
                        git 'https://github.com/DuduExlibris/testJenkins.git'
                        echo 'after checking out';
                      
                    }
                }
                stage('Build'){
                    steps{
                        
                          sh label: '', script: 'chmod +x ./Build.sh; ./Build.sh'
                          echo 'after building';
                    }
                }
                stage('JUnit'){
                    steps{
                        sh label: '', script: 'chmod +x ./Unit.sh; ./Unit.sh'
                        echo 'after running unit';
                    }
                }
                stage('Quality Gate'){
                    steps{
                         sh label: '', script: 'chmod +x ./Quality.sh; ./Quality.sh'
                          echo 'after running quality';
                    }
                }
                stage('Deploy'){
                    steps{
                         sh label: '', script: 'chmod +x ./Deploy.sh; ./Deploy.sh'
                          echo 'after running deploy';
                    }
                }
        }
        post{
            always {
                echo 'this will always run';
            }
            success{
                echo 'this will run only if successful';
            }
            failure{
                echo 'this will run on failiure';
            }
            changed{
                echo 'this will run only if the state of the pipline is changed';
                echo 'for example, if the pipeline was previously failing but is now passing';
            }
        }
 
    
}
