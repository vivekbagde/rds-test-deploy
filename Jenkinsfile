pipeline {
    agent any
    stages {
        stage('info') {
            environment {
                SECRET_VALUE = credentials('dbdevops')
            }
            steps {
                sh 'sudo docker run --rm -v $JENKINS_HOME/workspace/RDS-TEST-DEPLOY/flywayconf:/flyway/conf -v $JENKINS_HOME/workspace/RDS-TEST-DEPLOY/migrations:/flyway/sql -v $JENKINS_HOME/workspace/RDS-TEST-DEPLOY/driverpost:/flyway/drivers flyway/flyway -user=$SECRET_VALUE_USR -password=$SECRET_VALUE_PSW -baselineVersion=1.0 $CHOICE'
            }
        }
    }
}
