# Pengiun AEM project template

This is a project for 6.4 AEM. It is built using Maven Archtype 13. 

## Requirements
* AEM 6.4 + SP6 - aem-service-pkg-6.4.6.zip

## Relevant pieces

The relevant parts of the template are:

* apps/MelPengiun/components/content/bookcard - bookcard component: including dialog for authoring, clientlib for styling, and HTL for content.
* apps/MelPengiun/clientlibs/clientlib-base - which has the bookcard clientlibs embeded
* content/MelPengiun/en - example content: an authored example of the bookcard.
* content/MelPengiun/en/book-details - example pages: used for the bookcard to link to
* content/dam/MelPengiun - image assets: folder containing the book image for the bookcard to reference

* conf/MelPengiun/settings/wcm/templates/content-page/structure - page structure: edited to remove unused structure components and include page title
* apps/MelPengiun/components/content/title - title component: added basic styling

This component does not need a sling model so nothing to check in the core bundle.


## How to build

To build all the modules run in the project root directory the following command with Maven 3:

    mvn clean install

If you have a running AEM instance you can build and package the whole project and deploy into AEM with  

    mvn clean install -PautoInstallPackage
    
Or to deploy it to a publish instance, run

    mvn clean install -PautoInstallPackagePublish
    
Or alternatively

    mvn clean install -PautoInstallPackage -Daem.port=4503

Or to deploy only the bundle to the author, run

    mvn clean install -PautoInstallBundle

## Maven settings

The project comes with the auto-public repository configured. To setup the repository in your Maven settings, refer to:

    http://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html
