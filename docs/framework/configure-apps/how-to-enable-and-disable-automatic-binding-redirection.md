---
title: 'Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático'
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079548"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="d0d29-102">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="d0d29-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="d0d29-103">Al compilar aplicaciones en Visual Studio que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores, redirecciones de enlace se pueden agregar automáticamente al archivo de configuración de la aplicación para invalidar la unificación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d0d29-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="d0d29-104">Las redirecciones de enlace se agregan si la aplicación o sus componentes hacen referencia a más de una versión del mismo ensamblado, incluso si se especifican manualmente las redirecciones de enlace en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0d29-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="d0d29-105">La característica de redirección de enlace automática afecta a aplicaciones web y aplicaciones de escritorio tradicionales que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] o una versión posterior, aunque el comportamiento es ligeramente diferente para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="d0d29-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="d0d29-106">Puede habilitar la redirección de enlace automática si tiene aplicaciones existentes cuyo destino son versiones anteriores de .NET Framework o puede deshabilitar esta característica si desea conservar las redirecciones de enlace creadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="d0d29-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="d0d29-107">Deshabilitar las redirecciones de enlace automáticas en aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="d0d29-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="d0d29-108">Las redirecciones de enlace automáticas están habilitadas de forma predeterminada para las aplicaciones de escritorio tradicionales destinadas a [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d0d29-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="d0d29-109">Las redirecciones de enlace se agregan al archivo de configuración de salida (app.config) cuando la aplicación se compila y se invalida la unificación de ensamblados que puede producirse en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d0d29-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="d0d29-110">El archivo app.config de origen no se modifica.</span><span class="sxs-lookup"><span data-stu-id="d0d29-110">The source app.config file is not modified.</span></span> <span data-ttu-id="d0d29-111">Puede deshabilitar esta característica si modifica el archivo de proyecto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0d29-111">You can disable this feature by modifying the project file for the app.</span></span>

1. <span data-ttu-id="d0d29-112">Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0d29-112">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="d0d29-113">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d0d29-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="d0d29-114">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d0d29-114">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="d0d29-115">En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d0d29-115">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="d0d29-116">Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="d0d29-116">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="d0d29-117">En el archivo de proyecto, busque la siguiente entrada de propiedad:</span><span class="sxs-lookup"><span data-stu-id="d0d29-117">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="d0d29-118">Cambie `true` a `false`:</span><span class="sxs-lookup"><span data-stu-id="d0d29-118">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="d0d29-119">Habilitar redirecciones de enlace automáticas manualmente</span><span class="sxs-lookup"><span data-stu-id="d0d29-119">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="d0d29-120">Puede habilitar las redirecciones de enlace automáticas en las aplicaciones existentes destinadas a versiones anteriores de .NET Framework, o en casos donde se le pide automáticamente que agregue una redirección.</span><span class="sxs-lookup"><span data-stu-id="d0d29-120">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="d0d29-121">Si tiene como destino una versión más reciente de framework, pero no se le pide automáticamente que agregue una redirección, probablemente obtendrá resultados de compilación que le sugiere que reasignar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d0d29-121">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="d0d29-122">Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0d29-122">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="d0d29-123">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="d0d29-123">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="d0d29-124">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d0d29-124">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="d0d29-125">En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d0d29-125">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="d0d29-126">Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="d0d29-126">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="d0d29-127">Agregue el siguiente elemento en el primer grupo de propiedades de configuración (bajo la \<PropertyGroup > etiqueta):</span><span class="sxs-lookup"><span data-stu-id="d0d29-127">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="d0d29-128">La siguiente muestra un ejemplo de archivo de proyecto con el elemento insertado:</span><span class="sxs-lookup"><span data-stu-id="d0d29-128">The following shows an example project file with the element inserted:</span></span>

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

3. <span data-ttu-id="d0d29-129">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0d29-129">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="d0d29-130">Habilitar las redirecciones de enlace automáticas en aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="d0d29-130">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="d0d29-131">Las redirecciones de enlace automáticas se implementan de forma diferente para las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="d0d29-131">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="d0d29-132">Puesto que el archivo de configuración de origen (web.config) debe modificarse para las aplicaciones web, las redirecciones de enlace no se agregan de forma automática al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d0d29-132">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="d0d29-133">Sin embargo, Visual Studio le notifica los conflictos de enlace, por lo que podrá agregar redirecciones de enlace para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="d0d29-133">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="d0d29-134">Dado que siempre se le pedirá que agregue redirecciones de enlace, no es necesario deshabilitar explícitamente esta característica para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="d0d29-134">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="d0d29-135">Para agregar redirecciones de enlace a un archivo web.config:</span><span class="sxs-lookup"><span data-stu-id="d0d29-135">To add binding redirects to a web.config file:</span></span>

1. <span data-ttu-id="d0d29-136">En Visual Studio, compile la aplicación y compruebe si hay advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="d0d29-136">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="d0d29-137">![Advertencia de compilación para conflictos de referencia de ensamblado](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="d0d29-137">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="d0d29-138">Si hay conflictos de enlace de ensamblados, se mostrará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d0d29-138">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="d0d29-139">Haga doble clic en la advertencia, o seleccione la advertencia y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="d0d29-139">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="d0d29-140">Aparecerá un cuadro de diálogo que permite agregar automáticamente las redirecciones de enlace necesarias para el archivo web.config de origen.</span><span class="sxs-lookup"><span data-stu-id="d0d29-140">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>

   <span data-ttu-id="d0d29-141">![Cuadro de diálogo de permiso de redireccionamiento de enlace](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="d0d29-141">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="d0d29-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0d29-142">See also</span></span>

- [<span data-ttu-id="d0d29-143">\<bindingRedirect > elemento</span><span class="sxs-lookup"><span data-stu-id="d0d29-143">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="d0d29-144">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="d0d29-144">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
