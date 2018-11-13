---
title: Habilitar o deshabilitar las redirecciones de enlace generado automáticamente
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 284c2a08f2b78d2c6a1ab9752a3f2283e87fd734
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980838"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="220a7-102">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="220a7-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="220a7-103">Al compilar aplicaciones en Visual Studio que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores, redirecciones de enlace se pueden agregar automáticamente al archivo de configuración de la aplicación para invalidar la unificación de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="220a7-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="220a7-104">Las redirecciones de enlace se agregan si la aplicación o sus componentes hacen referencia a más de una versión del mismo ensamblado, incluso si se especifican manualmente las redirecciones de enlace en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="220a7-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="220a7-105">La característica de redirección de enlace automática afecta a las aplicaciones de escritorio y aplicaciones web que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] o una versión posterior, aunque el comportamiento es ligeramente diferente para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="220a7-105">The automatic binding redirection feature affects desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="220a7-106">Puede habilitar la redirección de enlace automática si tiene aplicaciones existentes destinadas a versiones anteriores de .NET Framework o puede deshabilitar esta característica si desea crear manualmente las redirecciones de enlace.</span><span class="sxs-lookup"><span data-stu-id="220a7-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to manually author binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="220a7-107">Deshabilitar las redirecciones de enlace automáticas en aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="220a7-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="220a7-108">Redirecciones de enlace automáticas están habilitadas de forma predeterminada para las aplicaciones de escritorio de Windows que tienen como destino el [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="220a7-108">Automatic binding redirects are enabled by default for Windows desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="220a7-109">Las redirecciones de enlace se agregan a la configuración de salida (**app.config**) cuando se compila la aplicación de archivo y anular la unificación de ensamblados que en caso contrario, es posible que tienen lugar.</span><span class="sxs-lookup"><span data-stu-id="220a7-109">The binding redirects are added to the output configuration (**app.config**) file when the app is compiled and override the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="220a7-110">El origen **app.config** no se modifica el archivo.</span><span class="sxs-lookup"><span data-stu-id="220a7-110">The source **app.config** file is not modified.</span></span> <span data-ttu-id="220a7-111">Puede deshabilitar esta característica si modifica el archivo de proyecto para la aplicación o anulando la selección de una casilla en las propiedades del proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="220a7-111">You can disable this feature by modifying the project file for the app or by deselecting a checkbox in the project's properties in Visual Studio.</span></span>

### <a name="disable-through-project-properties"></a><span data-ttu-id="220a7-112">Deshabilitar a través de las propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="220a7-112">Disable through project properties</span></span>

<span data-ttu-id="220a7-113">Si tiene Visual Studio 2017 versión 15.7 o posterior, puede deshabilitar fácilmente las redirecciones de enlace generado automáticamente en páginas de propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="220a7-113">If you have Visual Studio 2017 version 15.7 or later, you can easily disable autogenerated binding redirects in the project's property pages.</span></span>

1. <span data-ttu-id="220a7-114">Haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="220a7-114">Right-click the project in **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="220a7-115">En el **aplicación** página, desactive la **generar automáticamente redirecciones de enlace** opción.</span><span class="sxs-lookup"><span data-stu-id="220a7-115">On the **Application** page, uncheck the **Auto-generate binding redirects** option.</span></span>

3. <span data-ttu-id="220a7-116">Presione **Ctrl**+**S** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="220a7-116">Press **Ctrl**+**S** to save the change.</span></span>

### <a name="disable-manually-in-the-project-file"></a><span data-ttu-id="220a7-117">Deshabilitar manualmente en el archivo de proyecto</span><span class="sxs-lookup"><span data-stu-id="220a7-117">Disable manually in the project file</span></span>

1. <span data-ttu-id="220a7-118">Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="220a7-118">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="220a7-119">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="220a7-119">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="220a7-120">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="220a7-120">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="220a7-121">En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="220a7-121">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="220a7-122">Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="220a7-122">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="220a7-123">En el archivo de proyecto, busque la siguiente entrada de propiedad:</span><span class="sxs-lookup"><span data-stu-id="220a7-123">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="220a7-124">Cambie `true` a `false`:</span><span class="sxs-lookup"><span data-stu-id="220a7-124">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="220a7-125">Habilitar redirecciones de enlace automáticas manualmente</span><span class="sxs-lookup"><span data-stu-id="220a7-125">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="220a7-126">Puede habilitar las redirecciones de enlace automáticas en las aplicaciones existentes destinadas a versiones anteriores de .NET Framework, o en casos donde se le pide automáticamente que agregue una redirección.</span><span class="sxs-lookup"><span data-stu-id="220a7-126">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="220a7-127">Si tiene como destino una versión más reciente de framework, pero no se le pide automáticamente que agregue una redirección, probablemente obtendrá resultados de compilación que le sugiere que reasignar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="220a7-127">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="220a7-128">Abra el archivo de proyecto para editarlo mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="220a7-128">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="220a7-129">En Visual Studio, seleccione el proyecto en **el Explorador de soluciones**y, a continuación, elija **Abrir carpeta en el Explorador de archivos** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="220a7-129">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="220a7-130">En el Explorador de archivos, busque el archivo de proyecto (.csproj o .vbproj) y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="220a7-130">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="220a7-131">En Visual Studio, en **el Explorador de soluciones**, haga clic en el proyecto y elija **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="220a7-131">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="220a7-132">Haga clic en el proyecto descargado nuevo y, a continuación, elija **editar [nombredelproyecto.csproj]**.</span><span class="sxs-lookup"><span data-stu-id="220a7-132">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="220a7-133">Agregue el siguiente elemento en el primer grupo de propiedades de configuración (bajo la \<PropertyGroup > etiqueta):</span><span class="sxs-lookup"><span data-stu-id="220a7-133">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="220a7-134">La siguiente muestra un ejemplo de archivo de proyecto con el elemento insertado:</span><span class="sxs-lookup"><span data-stu-id="220a7-134">The following shows an example project file with the element inserted:</span></span>

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

3. <span data-ttu-id="220a7-135">Compile la aplicación.</span><span class="sxs-lookup"><span data-stu-id="220a7-135">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="220a7-136">Habilitar las redirecciones de enlace automáticas en aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="220a7-136">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="220a7-137">Las redirecciones de enlace automáticas se implementan de forma diferente para las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="220a7-137">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="220a7-138">Dado que la configuración de origen (**web.config**) archivo debe modificarse para las aplicaciones web, las redirecciones de enlace no se agregan automáticamente al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="220a7-138">Because the source configuration (**web.config**) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="220a7-139">Sin embargo, Visual Studio le notifica los conflictos de enlace, por lo que podrá agregar redirecciones de enlace para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="220a7-139">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="220a7-140">Dado que siempre se le pedirá que agregue redirecciones de enlace, no es necesario deshabilitar explícitamente esta característica para una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="220a7-140">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="220a7-141">Para agregar redirecciones de enlace a un **web.config** archivo:</span><span class="sxs-lookup"><span data-stu-id="220a7-141">To add binding redirects to a **web.config** file:</span></span>

1. <span data-ttu-id="220a7-142">En Visual Studio, compile la aplicación y compruebe si hay advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="220a7-142">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="220a7-143">![Advertencia de compilación para conflictos de referencia de ensamblado](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="220a7-143">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="220a7-144">Si hay conflictos de enlace de ensamblados, se mostrará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="220a7-144">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="220a7-145">Haga doble clic en la advertencia, o seleccione la advertencia y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="220a7-145">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="220a7-146">Un cuadro de diálogo que le permite agregar automáticamente el enlace es necesario que se redirige al origen de **web.config** aparece el archivo.</span><span class="sxs-lookup"><span data-stu-id="220a7-146">A dialog box that enables you to automatically add the necessary binding redirects to the source **web.config** file appears.</span></span>

   <span data-ttu-id="220a7-147">![Cuadro de diálogo de permiso de redireccionamiento de enlace](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="220a7-147">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="220a7-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="220a7-148">See also</span></span>

- [<span data-ttu-id="220a7-149">\<bindingRedirect > elemento</span><span class="sxs-lookup"><span data-stu-id="220a7-149">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="220a7-150">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="220a7-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
