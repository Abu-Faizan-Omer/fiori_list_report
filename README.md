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

 Video 6
 how to set default value in filter static
  <!-- <Annotation Term="Common.FilterDefaultValue" String="CAPM"/> -->

  how to set default value dynamically
 // THIS IS DYNAMICALLY DEFAULT VALUE
        onAfterRendering:function(){
              var oSmartFilterBar = this.byId("listReportFilter");
          var oDesigFilter =  oSmartFilterBar.getAllFilterItems()[1].getControl();
          oDesigFilter.setTokens([new sap.m.Token({
            key:'HR',
            text:"=HR"
          })]);
        },
 /// create custom action for table
extensionAPI - it is a predefine method which is already has some feature it hold all the selected rows 
// it send email message accordingly

<!-- sendNoticeToEmp: function(oEvent) {
            //MessageToast.show("Custom handler invoked.");
            var extensionAPI = this.extensionAPI //it is predefine method it grabs all the selected rows
            var aSelectContexts = extensionAPI.getSelectedContexts()
            var aEmails = []
            for(let i=0;i<aSelectContexts.length;i++){
                aEmails.push(aSelectContexts[i].getProperty("Email"))
            }
            var toList = aEmails.toString()
            var subject = "Warning notice on your Performance"
            var body = "Hi, \n we have notice your performance is not up to the mark.If you dont prove yourself there could be a chance of termination. \n thanks"

            sap.m.URLHelper.triggerEmail(toList,subject,body)
        } -->
///////////////////////////////////////////////////////////////////////////////////////////////////////

                                        Video 777777777777777

for 2nd page title and description with the help of HeaderInfo annotation

 <!-- // this is for 2nd page tittle and des -->
                    <PropertyValue Property="Title">
                        <Record Type="UI.DataField">
                            <PropertyValue Property="Value" Path="Name"/>
                        </Record>
                    </PropertyValue>
                    <PropertyValue Property="Description">
                        <Record Type="UI.DataField">
                            <PropertyValue Property="Value" Path="Empid"/>
                        </Record>
                    </PropertyValue>
///////////////
create headerfacets with the help of guide

 <!-- //data point pointing to odata designation and show on headerfacets -->
            <Annotation Term="UI.DataPoint" Qualifier="DPDesig">
                <Record Type="UI.DataPointType">
                    <PropertyValue Property="Title" String="Designation"/>
                    <PropertyValue Property="Value" Path="Desig"/>
                </Record>
            </Annotation>

     <!-- // this is data header facets which point to data element       -->
            <Annotation Term="UI.HeaderFacets">
                <Collection>
                    <Record Type="UI.ReferenceFacet">
                        <PropertyValue Property="Target" AnnotationPath="@UI.DataPoint#DPDesig"/>
                    </Record>
                </Collection>
            </Annotation>

/////
now we are adding employee info so that we new annotaion field group acheive by guided
it will add employee info and section part 
 <!-- <Annotation Term="UI.FieldGroup" Qualifier="FGEmpBasicInfo">
                <Record Type="UI.FieldGroupType">
                    <PropertyValue Property="Data">
                        <Collection>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Empid"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Name"/>
                            </Record>
                             <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Desig"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Doj"/>
                            </Record>
                             <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Email"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Skill"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Rating"/>
                            </Record>
                             <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Salary"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Status"/>
                            </Record>
                            <Record Type="UI.DataField">
                                <PropertyValue Property="Value" Path="Statuscriticality"/>
                            </Record>
                        </Collection>
                    </PropertyValue>
                </Record>
            </Annotation>
            <Annotation Term="UI.Facets">
                <Collection>
                    <Record Type="UI.ReferenceFacet">
                        <PropertyValue Property="Label" String="Employee Information"/>
                        <PropertyValue Property="ID" String="idEmpInfo"/>
                        <PropertyValue Property="Target" AnnotationPath="@UI.FieldGroup#FGEmpBasicInfo"/>
                    </Record>
                </Collection>
            </Annotation>
        </Annotations> -->
//create sub group inside employee info
 <!-- <Annotation Term="UI.Facets">   
                <Collection>
                <Record Type="UI.CollectionFacet">
                <!-- //create sub group under Employee information help of Colledtion facets -->
                <PropertyValue Property="Label" String="Employee Information"/>
                    <PropertyValue Property="Facets">
                        <Collection>
                             <Record Type="UI.ReferenceFacet">
                                <PropertyValue Property="Label" String="{@i18n>basicInfo}"/>
                                <PropertyValue Property="ID" String="idEmpInfo"/>
                                <PropertyValue Property="Target" AnnotationPath="@UI.FieldGroup#FGEmpBasicInfo"/>
                            </Record>
                             <Record Type="UI.ReferenceFacet">
                                <PropertyValue Property="Label" String="{@i18n>skillInfo}"/>
                                <PropertyValue Property="ID" String="idEmpSkill"/>
                                <PropertyValue Property="Target" AnnotationPath="@UI.FieldGroup#FGEmpSkill"/>
                            </Record>
                             <Record Type="UI.ReferenceFacet">
                                <PropertyValue Property="Label" String="{@i18n>performanceInfo}"/>
                                <PropertyValue Property="ID" String="idEmpPerf"/>
                                <PropertyValue Property="Target" AnnotationPath="@UI.FieldGroup#FGEmpPerf"/>
                            </Record>

                        </Collection>
                    </PropertyValue>
                </Record>

                   
                </Collection>
            </Annotation> -->

////////////////////////////////////////////////////////////////////////////////////////////////////////////

                            Video 8888888888888888888888
  here we are adding new project info for that we are creating new annotation line item annnotaion for project details 
  line item ===means table creation                          
  
  add charts

  //////////////////////////////////////////////////////////////////////////////////////////////////////

                        Video 99999999999
CRUD operation -we need to do only from backend from entity set (segw)
--> add edit button  by guide and (choose configure mass edit via dialog)   

--> how to go first page to second and second to third so need to write annotation in header Info annotation then it will redirect to third page

when click on project then it will show the project data so we are add headerInfo anootation
 <!-- <Annotations Target="ZF68FE_EMP_SRV.Project">
        <Annotation Term="UI.HeaderInfo" >
            <Record Type="UI.HeaderInfoType">
                <PropertyValue Property="TypeName" String="Project"/>
                <PropertyValue Property="TypeNamePlural" String="Projects"/>
                <PropertyValue Property="Title">
                    <Record Type="UI.DataField">
                        <PropertyValue Property="Value" Path="Empid"/>
                    </Record>
                </PropertyValue>
                <PropertyValue Property="Description">
                    <Record Type="UI.DataField">
                        <PropertyValue Property="Value" Path="Prjcode"/>
                    </Record>
                </PropertyValue>
            </Record>
        </Annotation> -->

        