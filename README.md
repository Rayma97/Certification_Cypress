Test case Ids that got passed:Tests_Scenarios_Certification11
1)CQSQB-V0E80-Q4CJL-U4R06  - Test scenario1 Firefox Mac os

2)INTCK-QPLE3-FZKHI-LMO15    - Test scenario2 Firefox mac os

3)JY7AA-ZWX4I-WT9G9-9TKPO  - Test scenario1 Chrome Windows 10

4)JED83-EVBKX-TTWEJ-GOYGB  - Test Scenario2 Chrome WIndows 10


Steps t follow
1)Install Cypress v9.6.0
npm install cypress@9.6.0 --save-dev

2)Install Xpath
  npm i cypress-xpath

3)Install Cypress audit
  npm i cypress-audit

4)Install Cypress axe for Test accessibility with axe-core
  npm i cypress-axenpm install --save-dev cypress-axe@0.14.0

Import it in cypress/support/index.js
  import 'cypress-axe'

5)Install Cypress lighthouse
  npm i -D cypress @cypress-audit/lighthouse

Add it in //cypress/support/index.js
  import '@cypress-audit/lighthouse/commands'


// cypress/plugins/index.js
  const { lighthouse, prepareAudit } = require('@cypress-audit/lighthouse')

      module.exports = (on, config) => {
          on('before:browser:launch', (browser = {}, launchOptions) => {
          prepareAudit(launchOptions)
      })

        on('task', {
        lighthouse: lighthouse(), // calling the function is important
      })
   }
   
   
6)Install the LambdaTest-Cypress CLI using the below command.
  npm install -g lambdatest-cypress-cli
  
7)Create lambdatest-config.json file that contains configurations like auth, capabilities, test settings, etc. which need to be successfully executed at LambaTest.
  lambdatest-cypress init
  
8)Pass the below command to run the test.
  lambdatest-cypress run

