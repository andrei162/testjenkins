pipeline {
    agent none
    stages {
        stage("Prebuild 1") {
            agent any
            steps {
                echo "Se initializeaza build-ul 1"
            }
        }
        stage("Prebuild 2") {
            agent any
            steps {
                echo "Se initializeaza build-ul 2"
            }
        }

        stage("Paralel builds") {
            parallel {
                stage("Build1") {
                    agent any

                    stages {
                        stage("build") {
                            steps {
                                echo "Build 1 success"
                            }
                        }
                        stage("deploy") {
                            steps {
                                echo "Deploy success"
                            }
                        }
                    }
                }

                stage("Build2") {
                    agent any
                    
                    stages {
                        stage("build") {
                            steps {
                                echo "Build 2 success"
                            }
                        }
                        stage("deploy") {
                            steps {
                                echo "Deploy 2 success"
                            }
                        }
                    }
                }
                stage("Build3") {
                    agent any
                    
                    stages {
                        stage("build") {
                            steps {
                                echo "Build 3 success"
                            }
                        }
                        stage("deploy") {
                            steps {
                                echo "Deploy 3 success"
                            }
                        }
                    }
                }
            }
        }
        stage("Post build") {
            parallel {
                stage("Post Build") {
                    agent any
                    steps {
                        echo "Post Build success"
                    }
                }
         stage("Final build") 
                  stage("Test final") {
                    agent any
                    steps {
                    echo "Build final success"
                    }
                 }
            }
        }
    }
}
