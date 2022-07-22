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
          stage('Cluster login') {
            steps {
               sh 'oc login https://api.foramanverma.cp.fyre.ibm.com:6443 -u kubeadmin -p IAK7b-Ea7MB-RUGPn-MWcqI --insecure-skip-tls-verify=true'
               sh 'oc new-project user-getting-started --display-name="Getting Started with OpenShift"'
               sh 'oc adm policy add-role-to-user view -z default -'
               sh 'oc new-app docker.io/aman1007/react:5.0 --name=parksmap'
               sh 'oc get service'
               sh 'oc create route edge reactapp --service=react'
               sh 'oc get route'
              }
         }
    }
}
