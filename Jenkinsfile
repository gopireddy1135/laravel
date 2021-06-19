pipeline {
   agent any
   stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'testingphp']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '609d39e4-f3ae-40b4-b26e-e4c5113508f4', url: 'https://github.com/gopireddy1135/laravel.git']]])
                sh "ls"
                sh "sudo apt-get install php"
                sh "sudo apt update"
                sh "sudo apt install curl"
                sh "curl -sS https://getcomposer.org/installer | php"
                sh "chmod +x composer.phar"
                sh "sudo mv composer.phar /usr/local/bin/composer"
                sh "composer -V"
                sh "sudo apt install phpunit"
                sh "cd vendor/bin/phpunit"
                sh "phpunit"
                sh "composer install"
            }
        }     
    }
}
