## Application Details
|               |
| ------------- |
|**Generation Date and Time**<br>Tue Apr 14 2026 07:16:29 GMT+0000 (Coordinated Universal Time)|
|**App Generator**<br>SAP Fiori Application Generator|
|**App Generator Version**<br>1.22.0|
|**Generation Platform**<br>SAP Business Application Studio|
|**Template Used**<br>List Report Page V2|
|**Service Type**<br>OData URL|
|**Service URL**<br>http://airdithanadev.airditsoftware.com:8010/sap/opu/odata/sap/ZF68FE_EMP_SRV|
|**Module Name**<br>zf68felrsegw|
|**Application Title**<br>Employee Management List Report Application|
|**Namespace**<br>com.listreport|
|**UI5 Theme**<br>sap_horizon|
|**UI5 Version**<br>1.136.0|
|**Enable TypeScript**<br>False|
|**Add Eslint configuration**<br>True, see https://www.npmjs.com/package/@sap-ux/eslint-plugin-fiori-tools#rules for the eslint rules.|
|**Main Entity**<br>EmployeeSet|
|**Navigation Entity**<br>toProjects|

## zf68felrsegw

An SAP Fiori application.

### Starting the generated app

-   This app has been generated using the SAP Fiori tools - App Generator, as part of the SAP Fiori tools suite.  To launch the generated application, run the following from the generated application root folder:

```
    npm start
```

- It is also possible to run the application using mock data that reflects the OData Service URL supplied during application generation.  In order to run the application with Mock Data, run the following from the generated app root folder:

```
    npm run start-mock
```

#### Pre-requisites:

1. Active NodeJS LTS (Long Term Support) version and associated supported NPM version.  (See https://nodejs.org)


//////////////////////////////////////////////////////////////////////

Video 2
create fiori app with fiori element and list report template in with the help of source name-connect to odata url=odata url
reflect field with the help of ANNOTATIONS 
write annotation with two type by manually and use guided development
//////////////////////////////////////////////////

V3
date validation from backend
date validition,rating ui

when i upadte in backend so i need to update in frontend as well so we need to go in the manifest.json right click and choose service manager and update then it will update in the frontend as well and give the suggestion

/////////////////////////////////////////////////////////////

video -4
HEADER INFO annotation ---- for title annotation
Selection Fields ------ for filter annotation

give meaning full name to every label so that end user will understand 
 <!-- </Annotations>
         <Annotations Target="ZF68FE_EMP_SRV.Employee/Desig">
            <Annotation Term="Common.Label" String="{@i18n>desig}">  
            </Annotation>
        </Annotations> -->

 ValueHelp annotation for create F4help dialogbox 

 <!-- //only one line this valuelistwithfixedvalues will convert f4help to drop down -->
            <!-- <Annotation Term="Common.ValueListWithFixedValues" Bool="true"/> -->
            
/////////////////////////////////////////////////////////////////////
                  Video 5

 Custom filter with the help of guide with three steps 
 apply single or multiple filter for status                  
 designation is mandatory to fill without that filling black filter will not work atleast select one filter which is designation

 //////////////////////////////////////