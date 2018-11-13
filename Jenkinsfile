node {
        stage ("Build"){
            echo '*** Build Starting ***'

            openshiftBuild bldCfg: 'cotd', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'quay-demo', showBuildLogs: 'false', verbose: 'false'


            echo '*** Build Complete ***'
        }
/*
        stage ("Promote image to Test"){

            openshiftTag(namespace: 'quay-demo', srcStream: 'cotd', srcTag: 'latest', destStream: 'cotd', destTag: 'testready')


        }
            
*/
        stage ("Deploy"){
            echo '*** Deployment Starting ***'
            openshiftDeploy depCfg: 'cotd', namespace: 'quay-demo', verbose: 'false', waitTime: ''
           // openshiftVerifyDeployment depCfg: 'cotd', namespace: 'cotd-test', replicaCount: '1', verbose: 'false', verifyReplicaCount: 'false', waitTime: ''
            echo '*** Deployment Complete ***'

            }
/*
   stage ("Promote image to Production"){

            openshiftTag(namespace: 'cotd-dev',srcStream: 'cotd', srcTag: 'testready', destStream: 'cotd', destTag: 'prodready')


        }
        stage ("Deploy and Verify in Prod Env"){


            echo '*** Deployment Starting ***'
            echo '*** Waiting for Input ***'
            input 'Should we deploy to Production?' 
            openshiftDeploy depCfg: 'cotd', namespace: 'cotd-prod', verbose: 'false', waitTime: ''
            openshiftVerifyDeployment depCfg: 'cotd', namespace: 'cotd-prod', replicaCount: '1', verbose: 'false', verifyReplicaCount: 'false', waitTime: ''
            echo '*** Deployment Complete ***'

        }
        */

} 