pipeline {
    agent any
        stages {
            stage('One') {
                steps {
                        echo 'Salut, sunt Ionucut'
                }
            }
        
            stage {('Two') {
                steps {
                    input('Ce vrei sa faci?')
                }
            }
        
            stage('Three') {
                when {
                    not {
                        branch "master"
                    }
                }
            
                steps {
                    echo "Salutareee!"
                }
            }    
            
            stage('Four') {
                parallel {
                    stage('Unit Test') {
                        steps {
                            echo "Ruleaza unit test..."
                        }
                    }
                    stage('Integrarea testului') {
                        agent {
                            docker {
                                reuseNode false
                                image 'ubuntu'
                            }
                        }
                    steps {
                        echo 'Ruleaza integrarea testului..'
                    }
                        
                    }
                    
                }
            }    
            }
        }
}
