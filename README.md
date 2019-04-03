# Actions on Google: Name Psychic Sample

This Java sample introduces permission requests for [user information](https://developers.google.com/actions/assistant/helpers#user_information) and
demonstrates [surface transfer capabilities](https://developers.google.com/actions/assistant/surface-capabilities#multi-surface_conversations)
when building Actions for Google Assistant and uses Google Maps Static API.

### Setup Instructions
**This sample uses Google Maps Static API and so requires [Pay as You Go](https://developers.google.com/maps/documentation/maps-static/usage-and-billing) billing enabled via the Google Cloud Platform console under your project.**

#### Action Configuration
1. From the [Actions on Google Console](https://console.actions.google.com/), add a new project (this will become your *Project ID*) > **Create Project** > under **More options** > **Conversational** card.
1. From the left navigation menu under **Build** > **Actions** > **Add Your First Action** > **BUILD** (this will bring you to the Dialogflow console) > Select language and time zone > **CREATE**.
1. In Dialogflow, go to **Settings** ⚙ > **Export and Import** > **Restore from zip**.
    + Follow the directions to restore from the `agent.zip` file in this repo.

#### App Engine Deployment & Webhook Configuration
When a new project is created using the Actions Console, it also creates a Google Cloud project in the background.

1. Obtain an API key through [Google Cloud Platform console](https://console.cloud.google.com) under your *Project ID*, **Menu ☰** > **APIs & Services** > **Credentials** > **Create Credentials** > **API key**
1. Replace `<YOUR_MAPS_KEY_HERE>` in `src/main/resources/config.properties` with the API key.
1. In the [Google Cloud Console API Library](https://console.cloud.google.com/apis/library), enable the Static Maps API under your *Project ID*.
1. Download & install the [Google Cloud SDK](https://cloud.google.com/sdk/docs/)
1. Configure the gcloud CLI and set your Google Cloud project to the name of your Actions on Google Project ID, which you can find from the [Actions on Google console](https://console.actions.google.com/) under Settings ⚙
    + `gcloud init`
    + `gcloud auth application-default login`
    + `gcloud components install app-engine-java`
    + `gcloud components update`
1. Deploy to [App Engine using Gradle](https://cloud.google.com/appengine/docs/flexible/java/using-gradle):
    + `gradle appengineDeploy` OR
    +  From within IntelliJ, open the Gradle tray and run the appEngineDeploy task.
1. Back in the [Dialogflow console](https://console.dialogflow.com), from the left navigation menu under **Fulfillment** > **Enable Webhook**, set the value of **URL** to `https://<YOUR_PROJECT_ID>.appspot.com` > **Save**.

#### Testing this Sample
1. In the [Dialogflow console](https://console.dialogflow.com), from the left navigation menu > **Integrations** > **Integration Settings** under Google Assistant > Enable **Auto-preview changes** >  **Test** to open the Actions on Google simulator.
1. Type `Talk to my test app` in the simulator, or say `OK Google, talk to my test app` to Google Assistant on a mobile device associated with your Action's account.

### References & Issues
+ Questions? Go to [StackOverflow](https://stackoverflow.com/questions/tagged/actions-on-google), [Assistant Developer Community on Reddit](https://www.reddit.com/r/GoogleAssistantDev/) or [Support](https://developers.google.com/actions/support/).
+ For bugs, please report an issue on Github.
+ To learn more about [Google Maps Static API](https://developers.google.com/maps/documentation/maps-static/intro).
+ Actions on Google [Documentation](https://developers.google.com/actions/extending-the-assistant)
+ [Webhook Boilerplate Template](https://github.com/actions-on-google/dialogflow-webhook-boilerplate-java) for Actions on Google.
+ More info about [Gradle & the App Engine Plugin](https://cloud.google.com/appengine/docs/flexible/java/using-gradle).
+ More info about deploying [Java apps with App Engine](https://cloud.google.com/appengine/docs/standard/java/quickstart).
 
### Make Contributions
Please read and follow the steps in the [CONTRIBUTING.md](CONTRIBUTING.md).
 
### License
See [LICENSE](LICENSE).
 
### Terms
Your use of this sample is subject to, and by using or downloading the sample files you agree to comply with, the [Google APIs Terms of Service](https://developers.google.com/terms/).
