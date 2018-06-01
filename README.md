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
![image4](https://user-images.githubusercontent.com/19189211/40848329-8236ad68-65dc-11e8-95f6-fa1c6fd564f4.png)


now connect esp8266 to your laptop for windows run mos.exe to see the interface of mongoose.
![image3](https://user-images.githubusercontent.com/19189211/40848138-f003fd92-65db-11e8-9f48-82da43b90ac9.png)
choose port,esp8266,demo.js and specify your wifi details.

now we are goint to register our device -:
1. gcloud projects list (note down your projectID of project)
2. go to terminal section of mongoose ui run the following command -: mos gcp-iot-setup --gcp-project YOUR_PROJECT_ID --gcp-region europe-west1 --gcp-registry iot-registry
![image5](https://user-images.githubusercontent.com/19189211/40848603-58e082b2-65dd-11e8-940d-0874162a76fb.png)


go to google cloud console click on the registry you will see the device has been registerd.
![image6](https://user-images.githubusercontent.com/19189211/40848847-f8823a22-65dd-11e8-8963-d15ef5c31560.png)



