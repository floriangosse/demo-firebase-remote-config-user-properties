Demo: Remote Config + User Properties
==============================

Preparation
---------------

1. Follow step 1 and 2 [here](https://firebase.google.com/docs/web/setup#register-app) to register a web app with your Firebase project
1. In the Firebase console, open your project
1. Select User Properties from the menu to view the User Properties dashboard
1. Create a user property with the key `some_flag`
1. Select Remote Config from the menu to view the Remote Config dashboard
1. Define a parameter with key `is_some_flag_true` and default value `null`
1. Click "Add value for condition" and "Define new condition"
1. Name it "some_flag is true" and add rule
    1. Set variable to "User Propertiy > `some_flag`"
    1. Set comparison method to "contains"
    1. Set expected value to `true`
1. Click "Create condition"
1. Set the value for the condition "some_flag is true" to `true`
1. Click "Add parameter", and then click "Publish changes"

Steps to reproduce the problem
---------------

1. Start, open the application and open the DevTools' console
1. Wait until you see the table with the results

_To check the problem again you have to remove Firebase's IndexDBs and the cookies._

### Actual results

Results show you that `is_some_flag_true` is `"null"`

### Expected results

Results show you that `is_some_flag_true` is `"true"`

### Notes

* If you only remove the IndexDBs but not the cookies you get the correct result on the second load of the application.