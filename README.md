# p2b-test-pipeline
 InstaPay P2B Automated Test

# Repository Directory Guide
    test
    ├── pipeline
    ├── environment
    ├── postman
    │   ├──────────────────────────────────├ invalid
    |   ├── valid                             ├── instapay_p2b_rfi_iso_invalid_runner.json
    |       ├── instapay_p2b_rfi_iso_valid_runner.json
    └── data
        ├──────────────────────────────────├ invalid
        ├── valid                             ├── invalid_test_data_biller1.csv
            ├── valid_test_data_biller1.csv   ├── invalid_test_data_biller2.csv
            ├── valid_test_data_biller2.csv

# Pre-requisite
* Jenkins
    - pipeline-utility-steps plugin

# Biller Onboarding
* Add valid test data csv of biller under test > data > valid
* Use naming convention invalid_test_data_<biller-name>.csv
* Add invalid test data csv of biller under test > data > invalid
* Use naming convention valid_test_data_<biller-name>.csv

# Jenkins Job Creation
* Create Pipeline Job in Jenkins
* Select pipeline script from SCM
* Select Git
* Enter https://github.com/pnbph-asid/p2b-test-pipeline.git as repository URL
* Enter main as branch
* Enter in script path test/pipeline/{Environment}/valid/Jenkinsfile
* Enter in script path test/pipeline/{Environment}/invalid/Jenkinsfile

# Test Execution
* Trigger Jenkins Job in Dev environment