---
title: "Configuración de su aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 064f396d0a757e5b2f5f12c4a2a836b74f5e66a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-your-application"></a>Configuración de su aplicación
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utiliza el sistema de configuración .NET y le permite configurar los servicios en el equipo y ámbito de aplicación.  
  
 Las opciones de configuración definidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentran en el grupo de la sección `<system.serviceModel>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo configurar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea los siguientes temas:  
  
-   [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]configuración de la aplicación en los archivos de configuración. NET, vea [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración  
 El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y programadores crear y modificar valores de configuración para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] los servicios mediante una interfaz gráfica de usuario. Con esta herramienta se puede administrar la configuración de los enlaces, comportamientos, servicios y diagnósticos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin editar directamente los archivos de configuración XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Edición de los archivos de configuración en Visual Studio  
 Para editar el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proyecto de servicio en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], haga clic en **el Explorador de soluciones** y elija la **Editar configuración de WCF** elemento de menú contextual. Esto inicia el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Si edita el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proyecto de servicio Web en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] con el botón secundario en **el Explorador de soluciones**, tenga en cuenta que la **Editar configuración de WCF** existe un elemento de menú contextual . Para solucionar este problema, haga clic en el **herramientas** menú y elija **Editor de configuración del servicio de WCF**. Después de eso, puede haga clic en un archivo de configuración y usar la **Editar configuración de WCF** elemento de menú contextual.  
  
## <a name="see-also"></a>Vea también  
 [Herramienta del editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
