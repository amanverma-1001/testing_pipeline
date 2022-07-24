pipeline {
    agent any
        stages{
            stage('Install oc'){
                steps{
                    sh 'wget -q https://mirror.openshift.com/pub/openshift-v4/clients/ocp/stable-4.6/openshift-client-linux.tar.gz'
                    sh 'tar xzvf openshift-client-linux.tar.gz --wildcards "oc"'
                    sh 'sudo mv -f oc /usr/local/bin/oc'
                    sh 'oc version'
                    }
            }

          stage('Image pushing to image registry')
          {
            steps{
                sh 'ssh '
                sh 'sudo su -'
                sh 'oc project default'
                sh 'oc get pod'

            }
          }

         
    }
}

