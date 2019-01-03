
# Live streaming of Automotive devices data using Custom Widgets within Cognos dashboard

In this Code Pattern, we will build a Cognos add-on to consume highly volatile streaming data, a dancing dashboard. 
The real time Dashboard will be able to display mix of data (volatile and non-volatile) can be shown on a single dashboard. Volatile data is extracted from external websites and in other words we are trying to build a Cognos add-on to consume streaming (Highly volatile) data like stock ticker or data from SCADA or IOT platform broadcast data. 
The idea is to build a dancing chart that captures volatile data and incrementally updates itself.

With the latest feature of Cognos 11.x Extensions, you now have the ability to add and remove elements in the IBM Cognos Analytics user interface for a perspective. An extension is a zip file that contains spec.json and optional images and js folders.


When the reader has completed this Code Pattern, they will understand how to:

* Build Cognos Custom Widgets
* Integrate Java Script built Extension within Cognos Dashboard
* Display mix of Historical and Live Streaming IoT data in Cognos Dashboard
* Interact with widgets within the same Cognos Dashboard

## Flow

![CDB_Cognos](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/DD_Flow.jpg)

1. Develop the code (includes spec.json, js, css, Images) to build Cognos Custom Widget (Extensions)
2. Bundle the code as a zip file.
3. Upload the zipped files into Cognos using Extensions.
4. Use the custom widget into Cognos Dashboard.
 


<!--Optionally, update this section when the video is created-->
# Watch the Video

[![](http://img.youtube.com/vi/Jxi7U7VOMYg/0.jpg)](https://www.youtube.com/watch?v=Jxi7U7VOMYg)

## Pre-requisites

* Cognos server - Have on-prim or SaaS offering of Cognos with `admin access`.
   > Note: Cognos version should be over 11.0.05.
   

# Steps

1. [Get the code](#1-get-the-code)
2. [Upload the zipped files into Cognos using Custom Widgets](#2-upload-the-zipped-files-into-cognos-using-custom-widgets)
3. [Create a Dashboard to consume the Custom Widget](#3-create-a-dashboard-to-consume-the-custom-widget)
4. [Run the Dashboard](#4-run-the-dashboard)
5. [Analyze the Dashboard](#5-analyze-the-dashboard)


## 1. Get the code

 - Clone the repo using the below command.
   ```
   git clone https://github.com/IBM/cognos-dancing-dashboard.git
   ```
   
 - In this repository, custom widget code is available at `./custom-widget-code`. Dowload the `CognosCustomWidget.zip` to your machine.
 
 -  The contents of zip file are as follows and we are providing as zip file (or bundled) to upload to Cognos as Custom widgets.
 
 ![Download_Code_Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/code.jpg)
 


## 2. Upload the zipped files into Cognos using Custom Widgets

- Launch Cognos BI server from the browser (Firefox is preferred). Use the url as per your Cognos Instance. 

Sample URL as follows: 
```
http://IP(or)localhost:port_number/bi/?perspective=home
```

![LaunchCognos](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/LaunchCognos.jpg)

- Under Cognos BI web browser, go to the `Manage -> Customization` option. See below screenshot for details.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/upload_BI.jpg)

-  Under Customization, use the Extension tab and click on upload icon to upload the `CognosCustomWidget.zip` file. See below screenshot for details.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/uploadBI1.jpg)

- You will see a successful upload message.

## 3. Create a Dashboard to consume the Custom Widget

- Open New Dashboard.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/db1.jpg)

- Select the blank template.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/db2.jpg)

- Click on the Newly created Custom Widget Icon.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/cw1.jpg)

- Drag and drop the Custom Widget to the Dashboard pane. See below screenshot for details.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/cw2.jpg)

- Adjust the dragged Custom widget to fit to the required height and width within the dashboard.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Adjust_Size.jpg)

- After adjusting the custom widget would look like below.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Adjust_Size1.jpg)

- Save the dashboard as 'Live Streaming of Device' under `My Folder` of Cognos Connection.

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Save_Dashboard.jpg)


## 4. Run the Dashboard

- Run the 'Live Streaming of Device' dashboard from the saved location.
 
 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/RunDashboard.jpg)

- You will see the dashboard with a list content which has 'DeviceA' last 24 hours data (Pressure, Temperature and Vibration)

 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Dashboard1.jpg)
 
- Click on any attribute (Pressure/Temperature/Vibration) column for live streaming. A pop up will appear to confirm the pressure live chart is going to be displayed. 
 
 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Popup.jpg)
 
-  See the below Live streaming of the line chart for pressure. 

 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Pressure.jpg)
 
- Similarly we can click on other metrics like Temperature and Vibration to see the live streaming of the data in the line chart.

 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/Temperature.jpg)
 
 ## 5. Analyze the Dashboard
 
 The dashboard displays both volatile and non-volatile data. Meaning, the static data is being read from the backend database and the real-time data is being read from the IoT device data through REST API's. Here we are generating the live data using the Random function. This dashboard is primarily useful for automobile manufacturing unit plant engineer who would want to monitor the devices at real-time. For example, if any of these metrics (Pressure/Temperatur/Vibration) go beyound the threshold points, then the plant would take a call to bring devices for maintenance. 
 

# Sample output

![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images//Sample_Output.jpg)

<!--Optionally, include any troubleshooting tips (driver issues, etc)-->

# Troubleshooting

* Error: Invalid File Name. (This error occurs while you are trying to upload the Custom widget Extension under Customization)

 ![Img](https://github.com/IBM/cognos-dancing-dashboard/blob/master/images/error1.png)

  > This is common error if the files are not bundled appropriately.
  
  
# Learn More

- [IBM Cognos Custom Widgets(Extensions)](https://www.ibm.com/support/knowledgecenter/en/SSEP7J_11.0.0/com.ibm.swg.ba.cognos.ag_manage.doc/c_ag_manage_extensions.html)


  
<!-- keep this -->
## License

[Apache 2.0](LICENSE)

