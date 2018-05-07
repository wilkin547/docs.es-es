---
title: Configuración de su aplicación
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 7dfd662fafa636e0fa97f118217ad1786d5aa444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-your-application"></a>Configuración de su aplicación
Windows Communication Foundation (WCF) utiliza el sistema de configuración de .NET y le permite configurar los servicios en el ámbito de equipo y aplicación.  
  
 Las opciones de configuración definidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentran en el grupo de la sección `<system.serviceModel>`. Para obtener más información sobre cómo configurar un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio, vea los temas siguientes:  
  
-   [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`. Para obtener más información acerca de la configuración de la aplicación en los archivos de configuración. NET, vea [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración  
 El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y programadores crear y modificar valores de configuración para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] los servicios mediante una interfaz gráfica de usuario. Con esta herramienta se puede administrar la configuración de los enlaces, comportamientos, servicios y diagnósticos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin editar directamente los archivos de configuración XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Edición de los archivos de configuración en Visual Studio  
 Para editar el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio de proyecto en Visual Studio, haga clic en **el Explorador de soluciones** y elija la **Editar configuración de WCF** elemento de menú contextual. Esto inicia el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Si edita el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proyecto de servicio Web en Visual Studio con el botón secundario en **el Explorador de soluciones**, tenga en cuenta que la **Editar configuración de WCF** existe un elemento de menú contextual. Para solucionar este problema, haga clic en el **herramientas** menú y elija **Editor de configuración del servicio de WCF**. Después de eso, puede haga clic en un archivo de configuración y usar la **Editar configuración de WCF** elemento de menú contextual.  
  
## <a name="see-also"></a>Vea también  
 [Herramienta del editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
