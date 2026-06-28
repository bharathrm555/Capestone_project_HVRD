@Library('Shared') _
pipeline {
    agent any
    
    environment{
        SONAR_HOME = tool "Sonar"
    }
    
    parameters {
        string(name: 'ADMIN_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
        string(name: 'FRONTEND_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
        string(name: 'BACKEND_DOCKER_TAG', defaultValue: '', description: 'Setting docker image for latest push')
    }
    
    stages {
        stage("Validate Parameters") {
            steps {
                script {
                    if (params.FRONTEND_DOCKER_TAG == '' || params.BACKEND_DOCKER_TAG == '' || params.ADMIN_DOCKER_TAG == '') {
                        error("ADMIN_DOCKER_TAG, FRONTEND_DOCKER_TAG and BACKEND_DOCKER_TAG must be provided.")
                    }
                }
            }
        }
        stage("Workspace cleanup"){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        
        stage('Git: Code Checkout') {
            steps {
                script{
                    code_checkout("https://github.com/bharathrm555/Capestone_project_HVRD.git","main")
                }
            }
        }
        
        stage("Trivy: Filesystem scan"){
            steps{
                script{
                    trivy_scan()
                }
            }
        }

        stage("OWASP: Dependency check"){
            steps{
                script{
                    owasp_dependency()
                }
            }
        }
        
        stage("SonarQube: Code Analysis"){
            steps{
                script{
                    sonarqube_analysis("Sonar", "Hero-Capstone-Project", "hero-capstone-project")
                }
            }
        }
        
        stage("SonarQube: Code Quality Gates"){
            steps{
                script{
                    sonarqube_code_quality()
                }
            }
        }
        
        
                
                
       
        
        stage("Docker: Build Images"){
            steps{
                script{
                        dir('admin'){
                            docker_build("shopnow-admin","${params.ADMIN_DOCKER_TAG}","bharathrm247")
                        }
                    
                        dir('backend'){
                            docker_build("shopnow-backend","${params.BACKEND_DOCKER_TAG}","bharathrm247")
                        }
                    
                        dir('frontend'){
                            docker_build("shopnow-frontend","${params.FRONTEND_DOCKER_TAG}","bharathrm247")
                        }
                }
            }
        }
        
        stage("Docker: Push to DockerHub"){
            steps{
                script{
                    docker_push("shopnow-admin","${params.ADMIN_DOCKER_TAG}","bharathrm247") 
                    docker_push("shopnow-backend","${params.BACKEND_DOCKER_TAG}","bharathrm247")
                    docker_push("shopnow-frontend","${params.FRONTEND_DOCKER_TAG}","bharathrm247")
                }
            }
        }
    }
    post{
        success{
            archiveArtifacts artifacts: '*.xml', followSymlinks: false
            build job: "shopnow-CD", parameters: [
                string(name: 'ADMIN_DOCKER_TAG', value: "${params.ADMIN_DOCKER_TAG}"),
                string(name: 'FRONTEND_DOCKER_TAG', value: "${params.FRONTEND_DOCKER_TAG}"),
                string(name: 'BACKEND_DOCKER_TAG', value: "${params.BACKEND_DOCKER_TAG}")
            ]
        }
    }
}
