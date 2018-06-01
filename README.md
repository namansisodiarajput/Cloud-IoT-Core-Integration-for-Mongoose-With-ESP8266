# Cloud-IoT-Core-Integration-for-Mongoose-With-ESP8266
we will integrate cloud iot core service for mongoose with the use of esp8266 node mcu.



install google cloud command line interface in your system - https://cloud.google.com/sdk/
install mongoose interface on your system - https://mongoose-os.com/software.html

after you successfully installed gcloud tool run the command prompt for following instruction -:
1. gcloud components install beta (installation for beta version)
2. gcloud auth login  (login with your google account)
3. gcloud projects create YOUR_PROJECT_NAME  (create your project and replace YOUR_PROJECT_NAME with name of your choice)
4. gcloud projects add-iam-policy-binding YOUR_PROJECT_NAME --member=serviceAccount:cloud-iot@system.gserviceaccount.com --role=roles/pubsub.publisher (add permission for iot core )
5. gcloud config set project YOUR_PROJECT_NAME  (set your current project)
6. gcloud beta pubsub subscriptions create --topic iot-topic iot-subscription (create pub sub subscription for your device data)
7. gcloud beta iot registries create iot-registry --region europe-west1 --event-pubsub-topic=iot-topic (create device registry)

go to view console of iot core -: https://cloud.google.com/iot-core/


now connect esp8266 to your laptop for windows run mos.exe to see the interface of mongoose.
![image3](https://user-images.githubusercontent.com/19189211/40848138-f003fd92-65db-11e8-9f48-82da43b90ac9.png)
