---
title: Configuración de su aplicación
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 04ddce4755ce30b7d46c3bd54024af08361d96ad
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536086"
---
# <a name="configuring-your-application"></a><span data-ttu-id="936e0-102">Configuración de su aplicación</span><span class="sxs-lookup"><span data-stu-id="936e0-102">Configuring Your Application</span></span>
<span data-ttu-id="936e0-103">Windows Communication Foundation (WCF) usa el sistema de configuración de .NET y permite configurar los servicios en el ámbito de la máquina y de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="936e0-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="936e0-104">Las opciones de configuración definidas por WCF se encuentran en el `<system.serviceModel>` grupo de secciones.</span><span class="sxs-lookup"><span data-stu-id="936e0-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="936e0-105">Para obtener más información sobre cómo configurar un servicio WCF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="936e0-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="936e0-106">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="936e0-106">Configuring Services</span></span>](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="936e0-107">Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`.</span><span class="sxs-lookup"><span data-stu-id="936e0-107">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="936e0-108">Para obtener más información sobre la configuración de la aplicación en los archivos de configuración de .NET, vea [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="936e0-108">For more information about application settings in .NET configuration files, see [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="936e0-109">Utilización del editor de configuración</span><span class="sxs-lookup"><span data-stu-id="936e0-109">Using the Configuration Editor</span></span>  
 <span data-ttu-id="936e0-110">La [herramienta editor de configuración de WCF (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y desarrolladores crear y modificar la configuración de los servicios WCF mediante una interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="936e0-110">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="936e0-111">Con esta herramienta, puede administrar la configuración de enlaces, comportamientos, servicios y diagnósticos de WCF sin tener que editar directamente los archivos de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="936e0-111">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="936e0-112">Edición de los archivos de configuración en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="936e0-112">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="936e0-113">Para editar el archivo de configuración de un proyecto de servicio de WCF en Visual Studio, haga clic con el botón derecho en él en **Explorador de soluciones** y elija el elemento de menú contextual **Editar configuración de WCF** .</span><span class="sxs-lookup"><span data-stu-id="936e0-113">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="936e0-114">Esto inicia la [herramienta editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="936e0-114">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="936e0-115">Si edita el archivo de configuración de un proyecto de servicio Web WCF en Visual Studio haciendo clic en él con el botón secundario en **Explorador de soluciones**, observe que falta el elemento de menú contextual **Editar configuración de WCF** .</span><span class="sxs-lookup"><span data-stu-id="936e0-115">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="936e0-116">Para solucionar este problema, haga clic en el menú **herramientas** y elija **Editor de configuración de servicio WCF**.</span><span class="sxs-lookup"><span data-stu-id="936e0-116">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="936e0-117">Después, puede hacer clic con el botón secundario en un archivo de configuración y usar el elemento de menú contextual **Editar configuración de WCF** .</span><span class="sxs-lookup"><span data-stu-id="936e0-117">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936e0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="936e0-118">See also</span></span>

- [<span data-ttu-id="936e0-119">Herramienta del editor de configuración (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="936e0-119">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="936e0-120">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="936e0-120">Configuring Services</span></span>](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
