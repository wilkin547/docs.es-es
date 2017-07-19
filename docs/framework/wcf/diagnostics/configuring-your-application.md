---
title: "Configuraci&#243;n de su aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Configuraci&#243;n de su aplicaci&#243;n
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza el sistema de configuración .NET y le permite configurar los servicios en el equipo y ámbito de aplicación.  
  
 Las opciones de configuración definidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentran en el grupo de la sección `<system.serviceModel>`.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo configurar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea los siguientes temas:  
  
-   [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la configuración de la aplicación en archivos de configuración de .NET, vea [Elemento \<appSettings\>](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## Utilización del editor de configuración  
 La [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite a los administradores y programadores crear y modificar la configuración de los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante una interfaz gráfica de usuario.Con esta herramienta se puede administrar la configuración de los enlaces, comportamientos, servicios y diagnósticos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin editar directamente los archivos de configuración XML.  
  
## Edición de los archivos de configuración en Visual Studio  
 Para editar el archivo de configuración de un proyecto de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], haga clic con el botón secundario en él en el **Explorador de soluciones** y elija el elemento de menú contextual **Editar configuración de WCF**.De esta forma se inicia la [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Si edita el archivo de configuración de un proyecto de servicio web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] haciendo clic con el botón secundario en él, en **Explorador de soluciones**, tenga en cuenta que falta el elemento de menú contextual **Editar configuración de WCF**.Para solucionar este problema, haga clic en el menú **Herramientas**, y seleccione **Editar configuración de servicio WCF**.Después, puede hacer clic con el botón secundario en un archivo de configuración y utilizar el elemento de menú contextual **Editar configuración de WCF**.  
  
## Vea también  
 [Herramienta del editor de configuración \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)   
 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)