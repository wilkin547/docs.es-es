---
title: "Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b6887706aeef3855c1e02c8b1379856022cdac04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="a6024-102">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="a6024-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="a6024-103">A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], al compilar aplicaciones destinadas a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], las redirecciones de enlace se pueden agregar automáticamente al archivo de configuración de la aplicación para anular la unificación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a6024-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="a6024-104">Las redirecciones de enlace se agregan si la aplicación o sus componentes hacen referencia a más de una versión del mismo ensamblado, incluso si se especifican manualmente las redirecciones de enlace en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6024-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="a6024-105">La característica de redirección de enlace automática afecta a las aplicaciones web y de escritorio tradicionales destinadas a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], aunque su comportamiento es ligeramente diferente para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="a6024-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="a6024-106">Puede habilitar la redirección de enlace automática si tiene aplicaciones existentes cuyo destino son versiones anteriores de .NET Framework o puede deshabilitar esta característica si desea conservar las redirecciones de enlace creadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="a6024-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="a6024-107">Deshabilitar las redirecciones de enlace automáticas en aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="a6024-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="a6024-108">Las redirecciones de enlace automáticas están habilitadas de forma predeterminada para las aplicaciones de escritorio tradicionales destinadas a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a6024-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="a6024-109">Las redirecciones de enlace se agregan al archivo de configuración de salida (app.config) cuando la aplicación se compila y se invalida la unificación de ensamblados que puede producirse en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a6024-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="a6024-110">El archivo app.config de origen no se modifica.</span><span class="sxs-lookup"><span data-stu-id="a6024-110">The source app.config file is not modified.</span></span> <span data-ttu-id="a6024-111">Puede deshabilitar esta característica si modifica el archivo de proyecto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6024-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="a6024-112">Para deshabilitar las redirecciones de enlace automáticas</span><span class="sxs-lookup"><span data-stu-id="a6024-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="a6024-113">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a6024-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a6024-114">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a6024-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="a6024-115">En el archivo de proyecto, busque la siguiente entrada de propiedad:</span><span class="sxs-lookup"><span data-stu-id="a6024-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="a6024-116">Cambie `true` a `false`:</span><span class="sxs-lookup"><span data-stu-id="a6024-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="a6024-117">Habilitar redirecciones de enlace automáticas manualmente</span><span class="sxs-lookup"><span data-stu-id="a6024-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="a6024-118">Puede habilitar las redirecciones de enlace automáticas en las aplicaciones existentes destinadas a versiones anteriores de .NET Framework, o en casos en que no se le pide automáticamente que agregue una redirección.</span><span class="sxs-lookup"><span data-stu-id="a6024-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="a6024-119">Si su objetivo es una versión más reciente del marco de trabajo, pero no se le pide automáticamente que agregue una redirección, probablemente obtendrá una salida de la compilación que le sugiere reasignar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a6024-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="a6024-120">Para agregar manualmente una propiedad de redirección de enlace automática</span><span class="sxs-lookup"><span data-stu-id="a6024-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="a6024-121">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a6024-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a6024-122">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a6024-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="a6024-123">Agregue el siguiente elemento en el primer grupo de propiedades de configuración (bajo la \<PropertyGroup > etiqueta):</span><span class="sxs-lookup"><span data-stu-id="a6024-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="a6024-124">En el ejemplo siguiente se muestra un archivo de proyecto con el elemento insertado.</span><span class="sxs-lookup"><span data-stu-id="a6024-124">The following shows an example project file with the element inserted.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>  
        <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
        <ProjectGuid>{123334}</ProjectGuid>  
        ...  
        <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>  
      </PropertyGroup>  
    ...  
    </Project>  
    ```  
  
4.  <span data-ttu-id="a6024-125">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6024-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="a6024-126">Habilitar las redirecciones de enlace automáticas en aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="a6024-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="a6024-127">Las redirecciones de enlace automáticas se implementan de forma diferente para las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="a6024-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="a6024-128">Puesto que el archivo de configuración de origen (web.config) debe modificarse para las aplicaciones web, las redirecciones de enlace no se agregan de forma automática al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6024-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="a6024-129">Sin embargo, Visual Studio le notifica los conflictos de enlace, por lo que podrá agregar redirecciones de enlace para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="a6024-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="a6024-130">Puesto que siempre se le preguntará si desea agregar redirecciones de enlace, no necesita deshabilitar explícitamente esta característica para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="a6024-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="a6024-131">Para agregar redirecciones de enlace a un archivo web.config</span><span class="sxs-lookup"><span data-stu-id="a6024-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="a6024-132">En Visual Studio, compile la aplicación y compruebe si hay advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="a6024-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="a6024-133">![Advertencia de compilación para conflictos de referencia de ensamblado](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="a6024-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="a6024-134">Si hay conflictos de enlace de ensamblados, se mostrará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="a6024-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="a6024-135">Haga doble clic en la advertencia.</span><span class="sxs-lookup"><span data-stu-id="a6024-135">Double-click the warning.</span></span> <span data-ttu-id="a6024-136">(Teclado: seleccione la advertencia y presione **ENTRAR**.)</span><span class="sxs-lookup"><span data-stu-id="a6024-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="a6024-137">Aparecerá un cuadro de diálogo que permite agregar automáticamente las redirecciones de enlace necesarias para el archivo web.config de origen.</span><span class="sxs-lookup"><span data-stu-id="a6024-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="a6024-138">![Cuadro de diálogo de permiso de redireccionamiento de enlace](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="a6024-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6024-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6024-139">See Also</span></span>  
 [<span data-ttu-id="a6024-140">\<bindingRedirect > elemento</span><span class="sxs-lookup"><span data-stu-id="a6024-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="a6024-141">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="a6024-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
