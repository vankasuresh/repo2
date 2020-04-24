pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    
            agent any
            steps{
                git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
            
            }
            
        }
        stage('compile'){
            agent any
            steps{
                sh 'mvn compile'
                
            } 
            
            }
            stage ('codereview'){
                agent any
                steps{
                    sh 'mvn pmd:pmd'
                }
            }
            stage ('UnitTest'){
                agent any
                steps{
                    git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
                    sh 'mvn test'
                }
            }
            stage ('metrixcheck'){
                agent any
                steps{
                    sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
                    
                }
            }
            stage ('packaging'){
                agent any
                steps{
                    sh 'mvn package'
                    
                }
            }
