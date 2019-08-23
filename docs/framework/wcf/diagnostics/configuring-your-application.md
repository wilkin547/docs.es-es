---
title: Configuración de su aplicación
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e096f4b64ada8b142e8b82c8877eec7f1b84637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939809"
---
# <a name="configuring-your-application"></a>Configuración de su aplicación
Windows Communication Foundation (WCF) usa el sistema de configuración de .NET y permite configurar los servicios en el ámbito de la máquina y de la aplicación.  
  
 Las opciones de configuración definidas por WCF se encuentran `<system.serviceModel>` en el grupo de secciones. Para obtener más información sobre cómo configurar un servicio WCF, vea los temas siguientes:  
  
- [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)  
  
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`. Para obtener más información sobre la configuración de la aplicación en los archivos de configuración de .net, consulte [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración  
 La [herramienta editor de configuración de WCF (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y desarrolladores crear y modificar la configuración de los servicios WCF mediante una interfaz gráfica de usuario. Con esta herramienta, puede administrar la configuración de enlaces, comportamientos, servicios y diagnósticos de WCF sin tener que editar directamente los archivos de configuración XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Edición de los archivos de configuración en Visual Studio  
 Para editar el archivo de configuración de un proyecto de servicio de WCF en Visual Studio, haga clic con el botón derecho en él en **Explorador de soluciones** y elija el elemento de menú contextual **Editar configuración de WCF** . Esto inicia la [herramienta editor de configuración (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
> Si edita el archivo de configuración de un proyecto de servicio Web WCF en Visual Studio haciendo clic en él con el botón secundario en **Explorador de soluciones**, observe que falta el elemento de menú contextual **Editar configuración de WCF** . Para solucionar este problema, haga clic en el menú **herramientas** y elija **Editor de configuración de servicio WCF**. Después, puede hacer clic con el botón secundario en un archivo de configuración y usar el elemento de menú contextual **Editar configuración de WCF** .  
  
## <a name="see-also"></a>Vea también

- [Herramienta del editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Configuración de servicios](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
