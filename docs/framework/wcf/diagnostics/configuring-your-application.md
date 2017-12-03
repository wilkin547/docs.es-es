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
# <a name="configuring-your-application"></a><span data-ttu-id="5c79f-102">Configuración de su aplicación</span><span class="sxs-lookup"><span data-stu-id="5c79f-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="5c79f-103"> utiliza el sistema de configuración .NET y le permite configurar los servicios en el equipo y ámbito de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c79f-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="5c79f-104">Las opciones de configuración definidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se encuentran en el grupo de la sección `<system.serviceModel>`.</span><span class="sxs-lookup"><span data-stu-id="5c79f-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5c79f-105"> cómo configurar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5c79f-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5c79f-106">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="5c79f-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="5c79f-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5c79f-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="5c79f-108">Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`.</span><span class="sxs-lookup"><span data-stu-id="5c79f-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5c79f-109">configuración de la aplicación en los archivos de configuración. NET, vea [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).</span><span class="sxs-lookup"><span data-stu-id="5c79f-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="5c79f-110">Utilización del editor de configuración</span><span class="sxs-lookup"><span data-stu-id="5c79f-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="5c79f-111">El [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y programadores crear y modificar valores de configuración para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] los servicios mediante una interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c79f-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="5c79f-112">Con esta herramienta se puede administrar la configuración de los enlaces, comportamientos, servicios y diagnósticos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin editar directamente los archivos de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="5c79f-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="5c79f-113">Edición de los archivos de configuración en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c79f-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="5c79f-114">Para editar el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proyecto de servicio en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], haga clic en **el Explorador de soluciones** y elija la **Editar configuración de WCF** elemento de menú contextual.</span><span class="sxs-lookup"><span data-stu-id="5c79f-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="5c79f-115">Esto inicia el [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5c79f-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c79f-116">Si edita el archivo de configuración de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proyecto de servicio Web en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] con el botón secundario en **el Explorador de soluciones**, tenga en cuenta que la **Editar configuración de WCF** existe un elemento de menú contextual .</span><span class="sxs-lookup"><span data-stu-id="5c79f-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="5c79f-117">Para solucionar este problema, haga clic en el **herramientas** menú y elija **Editor de configuración del servicio de WCF**.</span><span class="sxs-lookup"><span data-stu-id="5c79f-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="5c79f-118">Después de eso, puede haga clic en un archivo de configuración y usar la **Editar configuración de WCF** elemento de menú contextual.</span><span class="sxs-lookup"><span data-stu-id="5c79f-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c79f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c79f-119">See Also</span></span>  
 [<span data-ttu-id="5c79f-120">Herramienta del editor de configuración (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="5c79f-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="5c79f-121">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="5c79f-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="5c79f-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5c79f-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
