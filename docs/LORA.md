# LoRa

<p id="lora-information" class="anchor-link"></p>
<p id="overview-lora" class="anchor-link"></p>

## Overview
LoRa is a wireless technology developed to create the low-power, wide-area networks (LPWANs) required for machine-to-machine (M2M) and Internet of Things (IoT) applications. The technology offers a very compelling mix of long range, low power consumption and secure data transmission and is gaining significant traction in IoT networks being deployed by wireless network operators.

A network based on LoRa wireless technology can provide coverage that is greater in range compared to that of existing cellular networks. In fact, many mobile network operators have chosen to complement their existing cellular/wireless networks with a LPWAN based on LoRa technology because it is easy to plug into their existing infrastructure and also allows them to offer their customers a solution to serve more IoT battery-operated applications.

LoRa technology was originally developed by Semtech, but is now coordinated by the 300+ member LoRa Alliance, a non-profit organization focused on standardizing LoRa for IoT/M2M and creating a strong ecosystem to scale the technology. To date, the alliance has developed a global LPWAN specification, known as LoRaWAN™, to help standardize LPWANs and foster the adoption of these networks to enable IoT, M2M, smart city, and industrial applications.

<p id="how-it-works-lora" class="anchor-link"></p>


## How LoRaWAN works
LoRaWAN is a Data + Network Protocol built on top of LoRa. LoRaWAN targets the basic needs of LoRa usage for IoT by providing Addressing, Routing and Security.

Topology of a LoRaWAN network consists of several elements.

* **End Nodes:** End nodes are elements such as sensors, which are usually remotely located.
* **Concentrator / Gateway:** Gateways are access points for for end nodes (e.g. sensors), aggregating data and communicating that data to a central network server via standard IP connections. Several gateways can be co-located in an area and can transparently share a single connection to the network server.
* **Network Server:** The LoRa Network Server acts to eliminate duplicate packets, manages security and data rates.
* **Application Server:** Application Servers manage payload security and performs analysis to utilize sensor data. Cayenne operates as an Application Server.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160819110810/LoRaWAN.png" width="600" height="320" alt="Using Sketch Files"><br/><br/></p>

<p id="device-information-lora" class="anchor-link"></p>


## About DevEUIs

LoRa devices have a unique identifier (DevEUI) that is assigned to the device by the chip manufacturer. This identifier is used to uniquely identify the device on the network. Cayenne will need to know the DevEUI for your device, regardless of whether it is already registered, or if the device needs to be activated for the first time.

<p id="using-a-public-gateway-lora" class="anchor-link"></p>


## Using a public network
Using a public LoRa network is the easiest way to get started using LoRa. In order to get started using a public LoRa network, you will want to first verify that yours sensors will be covered by an appropriate Network Operator. Once you know which network operator you will connect with, you can purchase devices that work on that network. You will then need an account with that operator so that you can add your devices to the network.

In order to activate a LoRa device on a network, you will need to have an account with that network. Using Cayenne, you will not need your account information if the device has already been registered on the network. If you wish to use Cayenne to help activate the device on the network, however, you will need your account information handy so that you can provide this information in order to authenticate with the network and activate the device.

Cayenne currently supports the following LoRa networks. The list of networks that work with Cayenne will keep growing.

*   [Actility](#lora-actility)
*   [Senet](#lora-senet-network)


## Actility

**About Actility**

Actility is an industry leader in Machine to Machine (M2M) large scale infrastructure with ThingPark®, the new generation standard-based M2M communication platform. Actility is a winner of the French Ministry of Research competition, has obtained the Grand Prix of the Tremplin Entreprise and has been rewarded by Innov’ Eco and CleanTech République for its particularly innovative approach in its Internet Of Things (IoT) solutions.

**Using Actility with Cayenne**

Cayenne makes it easy to use your LoRa device and the Actility network. You will need to:

1. [Create / Log into your account on Actility's ThingPark portal](#lora-actility-create-account)
2. [Setup gateway device](#lora-actility-setup-gateway-device)
3. [Create Cayenne Routing Profile](#lora-actility-create-cayenne-routing-profile)
4. [Register your device on the ThingPark portal](#lora-actility-manually-register-device)
5. [Program/Flash your device](#lora-actility-programming-the-device)
6. [Add your device to your Cayenne dashboard](#lora-actility-add-device-to-cayenne)

We will walk you through these steps in the following sections.


### Create account

To create your Actility account, visit the <a href="http://actility.thingpark.com/thingpark-store/authentication" target="_blank">Actility ThingPark Portal</a>. Follow the **Create your account** process located there to get started.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Actility-portal-landing.png" width="600" height="363" alt="Actility"><br/><br/></p>


### Setup gateway device

In order for your LoRa devices to connect to the Actility network, you must have purchased and configured a gateway device. When using the Actility network, we recommend that you purchase and configure one of the following gateway devices:

+ For use in the European Union, we recommend the **Multitech Conduit EU868**
   + You can purchase a <a href="http://actility.thingpark.com/thingpark-store/development-kit/178-multitech-conduit-eu868.html" target="_blank">Multitech Conduit EU868 here</a>
+ For use in the United States of America, we recommend the **Multitech Conduit US915**
   + You can purchase a <a href="http://actility.thingpark.com/thingpark-store/development-kit/193-multitech-conduit-us915.html" target="_blank">Multitech Conduit US915 here</a>
   
**Be sure that you have an appropriate Actility gateway configured and working before continuing. Your devices will not be able to properly function without your gateway device in place.**


### Create Cayenne Routing Profile

<p style="text-align:center"><iframe width="480" height="270" src="https://www.youtube.com/embed/rpZo-GKd7mY" frameborder="0" allowfullscreen></iframe></p>

In order for data from your device to reach Cayenne, you must create an **AS Routing Profile** in the Actility portal. You only need to perform this step once. Any devices that you wish to add to Cayenne will then need to be configured to use this routing profile or Cayenne will not receive their data. To create this profile select the **AS routing profiles** entry on the portal. From the screen that appears, click on the **Add** button to begin creating a new profile.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-1.png" width="600" height="359" alt="create-routing-profile-1"><br/><br/></p>

Give your profile a name and click the **Create** button.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-2.png" width="600" height="145" alt="create-routing-profile-2"><br/><br/></p>

The *Routing Profile* screen will appear with details for your profile. We want to add a new route to our profile, select the **Add** button to begin doing so.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-3.png" width="600" height="360" alt="create-routing-profile-3"><br/><br/></p>

In the **Destinations** field, select the existing *ThingPark Cloud* and click on the **Edit** button. The *Edit destination* dialog will appear.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-4.png" width="600" height="359" alt="create-routing-profile-4"><br/><br/></p>

In the *Edit destination* dialog, change the dropdown for **Type** to *Third party AS (HTTP)*. In the **Destination** field, enter in the Cayenne Actility URL and then click on the **Edit** button to save your changes. 
```
https://longrangeapi.mydevices.com/longrange/api/actility/messages/add
```

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-5.png" width="600" height="284" alt="Cayenne URL"><br/><br/></p>

After saving your changes, you will be returned to the previous screen. Be sure to click on the **Save** button to save the changes to your profile. You may now continue with creating a device that uses this profile.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Create-Routing-Profile-6.png" width="600" height="359" alt="create-routing-profile-6"><br/><br/></p>

### Manually register device

Before you can use your LoRa device on the Actility network, it must be registered on the network. The following information will help guide you through this process using Actility's ThingPark portal.

**Log into the ThingPark portal**

If you aren't already logged in, start by going to the <a href="https://demo.thingpark.com/deviceManager/" target="_blank">Actility portal</a> and logging into your account. You will then see the Actility dashboard.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822144157/ThingPark-login2.png" width="300" height="362" alt="Actility"><br/><br/></p>

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160824134621/ThingPark-landing-dashboard.png" width="600" height="407" alt="Actility"><br/><br/></p>


**Create new device**

<p style="text-align:center"><iframe width="480" height="270" src="https://www.youtube.com/embed/hxhRwEalGvk" frameborder="0" allowfullscreen></iframe></p>

To get started with a new device, right-click on the **Devices** entry in the portal and select **Create device** from the menu that appears.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822155516/ThingPark-menu-expanded-Create-device.png" width="400" height="337" alt="Actility"><br/><br/></p>

The *New device* dialog will appear. To create a new device using the Actility portal, you will need to enter in all required information for completing the device creation. The process begins by selecting an appropriate activation mode from the **Device activation** field.

Actility supports two activation modes (OTAA, APB). In most cases, you will want to select Over the Air Activation (OTAA). Let's cover the information needed for both methods.

- [Over the Air Activation (OTAA)](#lora-actility-manually-register-device-over-the-air-activation-otaa)
- [Activation By Personalization (APB)](#lora-actility-manually-register-device-activation-by-personalization-apb)

#### Over the Air Activation (OTAA)

After selecting the OTAA activation mode, the list of fields will update to show you required fields. You will need to fill in all require fields to register & activate your device with Actility. Below you will find notes on the fields seen for OTAA and specific notes as they relate to what needs to be selected in order to work with Cayenne.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822144738/ThingPark-New-device.png" width="600" height="407" alt="Actility"><br/><br/></p>

+ Device identification
    + **Device EUI:** Enter the DevEUI for your device. This ID should come with the information included with your device, or can be found in the device configuration.
    + **Device Address:** Skip – When selecting OTAA activation, the device address will automatically be generated based on the DevEUI.
    + **Device Profile:** Actility uses this profile to correctly decode the payload, based on the device type, and display it on their dashboard. Be sure to select the correct profile for your device and which network it will be using.
    
        *TIP: You can refer to the [Supported devices section](#lora-actility-supported-devices) where we have more details on which Device Profile to select for devices.*
+ Application layer
    + **Application EUI:** Enter the AppEUI. The AppEUI is a global application ID that uniquely identifies the application provider (i.e., owner) of the device.

        *TIP: If you do not have an Applicate EUI, you can create one yourself. It must be a unique string composed of 16 alphanumeric characters.*
    + **Application key:** Enter the Appkey. The AppKey is a key specific for the end-device that is assigned by the application owner to the end-device and most likely derived from an application-specific root key exclusively known to and under the control of the application provider.

        *TIP: If you do not have an Applicate key, you can create one yourself. It must be a unique string composed of 32 alphanumeric characters.*
    + **Thingpark cloud config:** Skip – Cayenne does not require this optional field.
+ Network
    + **Connectivity plan:** Select an appropriate Actility plan here for activating your device under.
    + **AS routing profile:** Select the Cayenne route that you [created earlier](#lora-actility-create-cayenne-routing-profile) from the dropdown here. This will forward the information from your device to Cayenne so that once your device is online, Cayenne will receive its information.
+ Administrative data
    + **Device name:** Used by Actility. Cayenne does not use this information.
    + **Marker:** Used by Actility. Cayenne does not use this information.
    + **Administrative info:** Used by Actility. Cayenne does not use this information.
    + **Administrative location:** Used by Actility. Cayenne does not use this information.
+ Complete the device creation by clicking the **Create** button to create the device.

Once added, you will see your new device listed in the device list on the portal.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/ThingPark-device-list.png" width="600" height="406" alt="Actility"><br/><br/></p>

Once your device has been created, continue by making sure that your device has been [programmed/flashed](#lora-actility-programming-the-device).

#### Activation By Personalization (APB)

After selecting the APB activation mode, the list of fields will update to show you required fields. You will need to fill in all require fields to register & activate your device with Actility. Below you will find notes on the fields seen for APB and specific notes as they relate to what needs to be selected in order to work with Cayenne.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160825073849/ThingPark-New-device-APB.png" width="600" height="369" alt="Actility"><br/><br/></p>

+ Device identification
    + **Device EUI:** Enter the DevEUI for your device. This ID should come with the information included with your device, or can be found in the device configuration.
    + **Device Address:** When using APB, you will need to manually enter the hardware address here.
    + **Device Profile:** Actility uses this profile to correctly decode the payload, based on the device type, and display it on their dashboard. Be sure to select the correct profile for your device and which network it will be using.
    
        *TIP: You can refer to the [Supported devices section](#lora-actility-supported-devices) where we have more details on which Device Profile to select for devices.*
    + **Application session key:** Enter the AppSKey. The AppSKey is an application session key specific for the end-device. It is used by both the network server and the end-device to encrypt and decrypt the payload field of application-specific data messages.
    + **Network session key:** Enter the NwkSKey. The NwkSKey is a network session key specific for the end-device. It is used by both the network server and the end-device to calculate and verify the MIC (message integrity code) of all data messages to ensure data integrity. It is further used to encrypt and decrypt the payload field of a MAC only data messages.
+ Application layer
    + **Application EUI:** Enter the AppEUI. The AppEUI is a global application ID that uniquely identifies the application provider (i.e., owner) of the device.

        *TIP: If you do not have an Applicate EUI, you can create one yourself. It must be a unique string composed of 16 alphanumeric characters.*
    + **Application key:** Enter the Appkey. The AppKey is a key specific for the end-device that is assigned by the application owner to the end-device and most likely derived from an application-specific root key exclusively known to and under the control of the application provider.

        *TIP: If you do not have an Applicate key, you can create one yourself. It must be a unique string composed of 32 alphanumeric characters.*
    + **Thingpark cloud config:** Skip – Cayenne does not require this optional field.
+ Network
    + **Connectivity plan:** Select an appropriate Actility plan here for activating your device under.
    + **AS routing profile:** Select the Cayenne route that you [created earlier](#lora-actility-create-cayenne-routing-profile) from the dropdown here. This will forward the information from your device to Cayenne so that once your device is online, Cayenne will receive its information.
+ Administrative data
    + **Device name:** Used by Actility. Cayenne does not use this information.
    + **Marker:** Used by Actility. Cayenne does not use this information.
    + **Administrative info:** Used by Actility. Cayenne does not use this information.
    + **Administrative location:** Used by Actility. Cayenne does not use this information.
+ Complete the device creation by clicking the **Create** button to create the device.

Once added, you will see your new device listed in the device list on the portal.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/ThingPark-device-list.png" width="600" height="406" alt="Actility"><br/><br/></p>

Once your device has been created, continue by making sure that your device has been [programmed/flashed](#lora-actility-programming-the-device).

###  Programming the device

Some devices will come from your device supplier preprogrammed and ready to be used immediately. Other devices will require you to program the device manually. If your device is preprogrammed, it can now be deployed and connected to the network for usage.

If your device needs to be programmed, you should now proceed with programming/flashing the device. Because this process is different for each device, you should refer to the instructions for your device for any specific information you need to perform this step. If you need help, you can refer to the [Supported devices section](#lora-senet-network-supported-devices) where you will find Product page, Datasheet and User Guides for your device.

**NOTE: Be sure that your device is programmed and properly connected to the network at this time. Only after your device is programmed, online and properly forwarding data should you proceed with adding your device to Cayenne.**


### Add device to Cayenne

<p style="text-align:center"><iframe width="480" height="270" src="https://www.youtube.com/embed/u6QuVJCUTo4" frameborder="0" allowfullscreen></iframe></p>

Once your device has been registered, programmed, configured to forward data to Cayenne and is online, you can proceed with adding the device in Cayenne so that it appears in your dashboard.

From the Cayenne Dashboard, click **Add New** > **Device / Widget**.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160601122359/AddNew.jpg" width="260" height="252" alt="Actility"><br/><br/></p>

From the list of devices & widgets that appears, select the **LoRa** category and then the **Actility** Network option to view a list of Actility supported devices.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-Actility-menu.png" width="600" height="363" alt="Actility"><br/><br/></p>

After selecting the device that you wish to add, settings for that device will appear. In the following section, we’ll walk you through the settings needed for adding a previously registered device.

#### Already Registered

If your device has been previously registered on the Actility network, it can be quickly & easily added to Cayenne. Once added, your device and all of its sensors will appear in your dashboard.

**Items you will need:**

1.  Which [LoRa device](#lora-actility-supported-devices) is being added?
2.  Your device will need to have been previously registered on the network. Refer to [Manual device registration](#lora-actility-manually-register-device) if you need help with manually registering your device on a network.
3.  What is the unique [DevEUI](#lora-about-deveuis) for the device being added?

To see how easy it is, let’s walk through an example of connecting an [Adeunis LoRa Pulse](#supported-hardware-lora-devices-adeunis-lora-pulse) which was previously registered under an [Actility account](#lora-actility-create-account).

**1\. Choose the Network** <br/>
Make sure the **Actility** network is selected in the list of Networks.'

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-Actility-menu-1.png" width="600" height="363" alt="Actility"><br/><br/></p>

**2\. Select the Device** <br/>
Select your device from among the list supported Actility devices. In this case, we’ll select the **Adeunis LoRa Pulse**.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-Pulse-selected.png" width="600" height="363" alt="Actility"><br/><br/></p>

**3\. Enter Settings & Add device**

In order to add the device, Cayenne needs to know some information about the device and how it will be shown on the dashboard.

1.  Give the device a name. In our case, we’ll enter “LoRa Pulse” in the **Name** field.
2.  Enter the [DevEUI](#lora-about-deveuis) for this device into the **DevEUI** field.
3.  Our device has been previously manually registered with Actility. Select “Already Registered” in the **Activation Mode** field.
4.  Click **Add LoRa device**.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-Device-Actility-LoRa-Pulse-already-registered.png" width="600" height="363" alt="Actility"><br/><br/></p>

The LoRa Pulse has been added to your dashboard and Cayenne will automatically add widgets for the sensors on the device. You can now [track the location](#features-asset-tracking) of your device as well as examine the current status of the water, gas, electricity & heat sensors on the device.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/LoRa-dashboard.png" width="600" height="363" alt="Actility"><br/><br/></p>


### Supported devices

**Actility network devices supported by Cayenne**
Cayenne currently supports the following devices on the Actility network. Support for more devices is constantly ongoing.

*   [Adeunis LoRa Demonstrator](#supported-hardware-lora-devices-adeunis-lora-demonstrator)
*   [Adeunis LoRa Field Test Device](#supported-hardware-lora-devices-adeunis-lora-field-test-device)
*   [Adeunis LoRa Pulse](#supported-hardware-lora-devices-adeunis-lora-pulse)
*   [Adeunis LoRa Sensors](#supported-hardware-lora-devices-adeunis-lora-sensors)
*   [Ascoel CO2](#supported-hardware-lora-devices-ascoel-ascoel-co2)
*   [Ascoel Door Switch](#supported-hardware-lora-devices-ascoel-ascoel-door-switch)
*   [Ascoel Motion Sensor](#supported-hardware-lora-devices-ascoel-ascoel-motion-sensor)
*   [Elsys ELT-1](#supported-hardware-lora-devices-elsys-elsys-elt-1)
*   [Elsys ERS](#supported-hardware-lora-devices-elsys-elsys-ers)
*   [Elsys ESM5k](#supported-hardware-lora-devices-elsys-elsys-esm5k)
*   [GlobalSat LS-111 CO2](#supported-hardware-lora-devices-globalsat-globalsat-ls-111-co2)
*   [GlobalSat LT-100](#supported-hardware-lora-devices-globalsat-globalsat-lt-100)
*   [Multitech mDotBox](#supported-hardware-lora-devices-multitech-mdotbox)
*   [NKE Watteco Smart Plug](#supported-hardware-lora-devices-nke-watteco-watteco-smart-plug)
*   [NKE Watteco THr](#supported-hardware-lora-devices-nke-watteco-thr)
*   [Rising HF RHF1S001](#supported-hardware-lora-devices-rising-hf-rising-hf-rhf1s001)
*   [Semtech LoRa Motes EU](#supported-hardware-lora-devices-semtech-lora-motes-eu)
*   [Semtech LoRa Motes US](#supported-hardware-lora-devices-semtech-lora-motes-usa)

**Actility Device Profiles by device**

When setting up your device on Actility's ThingPark portal, you must select the correct **Device Profile** for your device. Below are some guidelines on which profile to select.

+ For devices used in European Union:
  + Select the Profile **LoRaWAN 1.0 class A - Rx2-SF12**
+ For devices use in United States of America:
  + Select the Profile **LoRaWAN 1.0 class A -US- Rx2-SF12**
+ Exceptions to the above:
  + If you are using the **NKE Watteco SmartPlug**, use the class C version of above configs depending on which region you are in.

    For example, with the SmartPlug being used in the US, select **LoRaWAN 1.0 class C (-US-) Rx2-SF12**
    And in the EU, select **LoRaWAN 1.0 class C - Rx2-SF12**


## Senet Network

**About Senet**

Senet, a contributing member of the LoRa® Alliance, is the first and only public provider in North America of low-power wide-area networks (LPWANs) with its class-leading LoRa® modulation for IoT and M2M applications.

**Using Senet with Cayenne**

Cayenne makes it easy to use your LoRa device and the Senet network. You will need to:

1. [Create / Log into your account on the Senet portal](#lora-senet-network-create-account)
2. [Setup gateway device](#lora-senet-network-setup-gateway-device)
3. [Register your device on the Senet portal](#lora-senet-network-manual-register-device)
4. [Setup traffic forwarding to Cayenne](#lora-senet-network-setup-device-forwarding-to-cayenne)
5. [Program/Flash your device](#lora-senet-network-programming-the-device)
6. [Add your device to your Cayenne dashboard](#lora-senet-network-add-device-to-cayenne)

We will walk you through these steps in the following sections.


### Create account

To create your Senet account, visit the <a href="https://portal.senetco.com/" target="_blank">Senet Portal</a>. Follow the **Register as a new user** process located there to get started.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-portal-register-account.png" width="600" height="363" alt="Senet"><br/><br/></p>


### Setup gateway device

In order for your LoRa devices to connect to the Senet network, you should purchase and configure a gateway device. When using the Senet network, it is recommended that you use a MultiConnect Conduit gateway device. You can find links to an appropriate LoRa version of this device on the <a href="http://multitech.com/brands/multiconnect-conduit" target="_blank">Multitech MultiConnect Conduit page</a>.

**Be sure that your devices are covered by the Senet network, including having an appropriate gateway configured and working if needed, before continuing. Your devices will not be able to properly function without your gateway device in place.**

#### Register new gateway device

If you need to register a new gateway device, the Senet portal has instructions and the software for doing so. To begin this process, log into your Senet account and click on the **Download gateway software** link. This will open a detailed guide that Senet has created for the process of registering and installing software on the Multitech MultiTech Conduit gateway.

**Note:** Gateway Registration and Software Installation is only required for devices that are new to the Senet Network. If Senet provided your device no further action is necessary.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-access-gateway-guide.png" width="600" height="299" alt="senet-access-gateway-guide"><br/><br/></p>

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-downlod-gateway-software.png" width="600" height="359" alt="senet-downlod-gateway-software"><br/><br/></p>


### Manual register device

Before you can use your LoRa device on the Senet network, it must be registered on the network using the Senet portal. The following information will help guide you through this process.

**Log into the Senet portal**

Start by going to the <a href="https://portal.senetco.com/" target="_blank">Senet portal</a> and logging into your account. Once logged in, you can proceed with registering a new device.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822125129/Senet-login.png" width="600" height="318" alt="Senet"><br/><br/></p>

**Register new device**

<p style="text-align:center"><iframe width="480" height="270" src="https://www.youtube.com/embed/CrY-wAw58Ts" frameborder="0" allowfullscreen></iframe></p>

To get started with a new device, click on the **Register new device** button. The *New node* screen will appear.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822125357/Senet-register-button-hlt.png" width="600" height="336" alt="Senet"><br/><br/></p>

From the *New node* screen, enter in the **Device ID** (this will be the *DevEUI* located on the device or given to you when purchased) and a description for the device. Click **Submit** to complete registering the device.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822125416/Senet-new-node.png" width="600" height="291" alt="Senet"><br/><br/></p>

Click on the **Back to Node List** button to return to the landing screen. Your device will now appear in the list of devices shown here.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-landing-dash.png" width="600" height="336" alt="senet-landing-dash"><br/><br/></p>


### Setup device forwarding to Cayenne

<p style="text-align:center"><iframe width="480" height="270" src="https://www.youtube.com/embed/k7V0FzuFf-I" frameborder="0" allowfullscreen></iframe></p>

In order for Cayenne to be able to able to receive your device’s information, you will need to setup packet forwarding. To do so, click on the device in the device list and its dashboard screen will open.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822125444/Senet-device-dashboard.png" width="600" height="410" alt="Senet"><br/><br/></p>

With the device dashboard screen open, click on the **cogwheel** menu and select **Device Edit**. The *Device Setup/Edit* screen appears.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160822125508/Senet-menu-device-edit.png" width="600" height="208" alt="Senet"><br/><br/></p>

From the *Device Setup/Edit* screen we can setup the device so that it forwards data to Cayenne. To do so, enter the following information:

1. From the **Forward To** dropdown select the **HTTP Post** option.
2. Leave the **Packet Format** at its default value of *JSON*.
3. Make sure the **Forward RF Data** checkbox is selected to see signal strength data for your device in Cayenne.
4. Enter in the Cayenne URL for the Senet API into the **URL** field.

   ```
   https://longrangeapi.mydevices.com/longrange/api/senet/messages/add
   ```
5. Click the **Update** button to save changes.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-device-setup-using-URL.png" width="600" height="216" alt="senet-device-setup-using-url"><br/><br/></p>

###  Programming the device

Some devices will come from your device supplier preprogrammed and ready to be used immediately. Other devices will require you to program the device manually. If your device is preprogrammed, it can now be deployed and connected to the network for usage.

If your device needs to be programmed, you should now proceed with programming/flashing the device. Because this process is different for each device, you should refer to the instructions for your device for any specific information you need to perform this step. If you need help, you can refer to the [Supported devices section](#lora-senet-network-supported-devices) where you will find Product page, Datasheet and User Guides for your device.

**NOTE: Be sure that your device is programmed and properly connected to the network at this time. Only after your device is programmed, online and properly forwarding data should you proceed with adding your device to Cayenne.**

*TIP: You should see data being reported on the Senet portal's device list for your device. If you do not, double check the values entered for your device and consider programming/flashing the device again.*

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Senet-landing-dash.png" width="600" height="336" alt="senet-landing-dash"><br/><br/></p>


### Add device to Cayenne

Once your device has been registered, programmed, configured to forward data to Cayenne and is online, you can proceed with adding the device in Cayenne so that it appears in your dashboard.

From the Cayenne dashboard, click **Add New** > **Device / Widget**.

<p style="text-align:center"><br/><img src="http://d1nocd4j7qtmw4.cloudfront.net/wp-content/uploads/20160601122359/AddNew.jpg" width="200" height="192" alt="Senet"><br/><br/></p>

From the list of devices & widgets that appears, click **LoRa** and select the **Senet** Network option to view a list of Senet supported devices.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-Senet-menu.png" width="600" height="362" alt="Senet"><br/><br/></p>

After selecting the device that you wish to add, settings for that device will appear. In the following section, we’ll walk you through the settings needed for adding a previously registered device.

#### Already Registered

Once your device has been previously registered on the Senet network, it can be quickly & easily added to Cayenne. Once added, your device and all of its sensors will appear in your dashboard.

**Items you will need:**

1.  Which [LoRa device](#lora-senet-network-supported-devices) is being added?
2.  Your device will need to have been previously registered on the network. Refer to [Manual device registration](#lora-senet-network-manual-register-device) if you need help with manually registering your device on the network.
3.  What is the unique [DevEUI](#lora-about-deveuis) for the device being added?

To see how easy it is, let’s walk through an example of connecting an [Multitech mDotBox](#supported-hardware-lora-devices-multitech-mdotbox) which was previously registered under a [Senet account](#lora-senet-network-create-account).

**1\. Choose the Network** <br/>
Make sure the **Senet** network is selected in the list of Networks.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-Senet-menu-1.png" width="600" height="362" alt="Senet"><br/><br/></p>

**2\. Select the Device** <br/>
Select your device from among the list supported Senet devices. In this case, we’ll select the **Multitech mDotBox**.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-LoRa-device-mDotBox-selected.png" width="600" height="362" alt="Senet"><br/><br/></p>

**3\. Enter Settings & Add device** <br/>
In order to add the device, Cayenne needs to know some information about the device and how it will be shown on the dashboard.

1.  Give the device a name. In our case, we’ll enter “mDotBox” in the **Name** field.
2.  Enter the [DevEUI](#lora-about-deveuis) for this device into the **DevEUI** field.
3.  Our device has been previously manually registered with Senet. Make sure “Already Registered” is selected in the **Activation Mode** field.
4.  Click **Add LoRa device**.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/Add-Device-Senet-mDotBox-already-registered.png" width="600" height="362" alt="Senet"><br/><br/></p>

The Multitech mDotBox device has been added to your dashboard and Cayenne will automatically add widgets for the sensors on the device. You can now [track the location](#features-asset-tracking) of your device as well as examine the current status of the various sensors on the device.

<p style="text-align:center"><br/><img src="http://www.cayenne-mydevices.com/CayenneStaging/wp-content/uploads/LoRa-dashboard.png" width="600" height="363" alt="Actility"><br/><br/></p>

### Supported devices

**Senet network devices supported by Cayenne**

Cayenne currently supports the following devices on the Senet network. Support for more devices is constantly ongoing.

*   [Adeunis LoRa Field Test Device](#supported-hardware-lora-devices-adeunis-lora-field-test-device)
*   [Ascoel CO2](#supported-hardware-lora-devices-ascoel-ascoel-co2)
*   [Ascoel Door Switch](#supported-hardware-lora-devices-ascoel-ascoel-door-switch)
*   [Ascoel Motion Sensor](#supported-hardware-lora-devices-ascoel-ascoel-motion-sensor)
*   [Elsys ELT-1](#supported-hardware-lora-devices-elsys-elsys-elt-1)
*   [Elsys ERS](#supported-hardware-lora-devices-elsys-elsys-ers)
*   [Elsys ESM5k](#supported-hardware-lora-devices-elsys-elsys-esm5k)
*   [GlobalSat LS-111 CO2](#supported-hardware-lora-devices-globalsat-globalsat-ls-111-co2)
*   [GlobalSat LT-100](#supported-hardware-lora-devices-globalsat-globalsat-lt-100)
*   [Multitech mDotBox](#supported-hardware-lora-devices-multitech-mdotbox)
*   [NKE Watteco Smart Plug](#supported-hardware-lora-devices-nke-watteco-watteco-smart-plug)
*   [NKE Watteco THr](#supported-hardware-lora-devices-nke-watteco-thr)
*   [Rising HF RHF1S001](#supported-hardware-lora-devices-rising-hf-rising-hf-rhf1s001)
*   [Semtech LoRa Motes US](#supported-hardware-lora-devices-semtech-lora-motes-usa)
