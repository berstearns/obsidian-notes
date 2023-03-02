# the process to publish a app in google play involves 
# building hte apk
# generating an .aab file


## how i build the aab ? 


I created a script to generate the apk.

for the signed .aab 

## step 1
sudo keytool -genkey -v -keystore rnTSgitlabCICDExample-upload.keystore -alias rnTSgitlabCICDExample-upload -keyalg RSA -keysize 2048 -validity 10000

## step 2
on the android folder run
./gradlew bundleRelease
