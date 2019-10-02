<table width=100% border=0>
<tr ><td colspan=2><h1>SAP Cloud Platform</h1></td></tr>
<tr><td><h3>Open Connectors</h3></td><td width=66%></br>&nbsp;S4HC APIs and Open Connectors Dev</td>
</table>

## Description

This info file contains links to code, help docs, etc. relevant to the Developing with the S4H Cloud APIs and Open Connectors series. Please note that this info file is a work in progress and subject to changes and additions.

We will build on elements from the previous videos in the [Getting Started with the S/4HANA Cloud API's](gettingstarteds4hcloudapis.md) series where we used the Planned Orders API and built a Destination off that managed API. 

We will consume the Planned Orders API in a new SAPui5 application in the Neo environment in SAP Cloud Platform. The application will convert the data into comma separated format and then upload it as a .csv file into Google Drive.

The application is able to interact with the Google Drive API through the SAP Open Connectors service which will be introduced in the first video.

<img src="../images/api.jpg">

## <a name="gss4hapi"></a>S4H Cloud APIs and Open Connectors Application
1) [Video 1 - Getting Started with Open Connectors - Using the Google Drive API](#v1ocgda)
1) [Video 2 - Creating a SAPUI5 App in SAP Cloud Platform - Consuming an S4HC API Service](#v2sascp)
1) [Video 3 - Finishing up the SAPUI5 App - Adding in the Open Connectors Pieces](#v3sascpoc)

#### Prerequisites

* You have access to a configured S/4HANA Cloud (non-Trial) system.
* You have set up an SAP Cloud Platform (Trial or Starter) account.
* You have completed the steps in [Getting Started with the S/4HANA Cloud API's](gettingstarteds4hcloudapis.md).
* You have a Google account.

#### <a name="v1ocgda"></a>Video 1 - Getting Started with Open Connectors - Using the Google Drive API

In this video we will create a new project in the Google API's and set up authentication to this app through Cloud Elements.  We will configure a new SCP Cloud Connector instance using the Google Drive connector using oauth via Cloud Elements.

Relevant Links:

* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[SAP Open Connectors](https://help.openconnectors.ext.hana.ondemand.com/home)
* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Cloud Elements](https://cloud-elements.com/)

#### <a name="v2sascp"></a>Video 2 - Creating a SAPUI5 App in SAP Cloud Platform - Consuming an S4HC API Service

In this video we will create a new SAPUI5 application that will consume an S/4HANA Cloud API. This will be based on the Planned Orders service that we have been using in our other getting started videos.

We will build on elements from previous videos where we used the Planned Orders API and built a Destination off that managed API. We will show how to consume a service from that API in an SAPUI5 application.

*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Code Used in This Video](/code/GglDrvApp.txt)

#### <a name="v3sascpoc"></a>Video 3 - Finishing up the SAPUI5 App - Adding in the Open Connectors Pieces

#### Additional Information

This video series is based on the following blogs.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Simplify Integration with third-party application with SAP Cloud Platform Open Connectors](https://blogs.sap.com/2018/09/24/blog-series-simplify-integration-with-third-party-application-with-sap-cloud-platform-open-connectors/)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Upload data from Fiori application into Google Drive using SAP Cloud Platform Open Connectors](https://blogs.sap.com/2017/12/05/part-2-discover-explore-and-consume-s4-hana-cloud-apis-in-sap-api-business-hub/)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[SAP API Management – Managing 3rd Party services via Open Connector Instances](https://blogs.sap.com/2019/02/20/sap-api-management-managing-3rd-party-services-via-open-connector-instances/)


