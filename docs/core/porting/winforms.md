---
title: Migración de una aplicación de Windows Forms a .NET Core
description: Se detalla cómo migrar una aplicación de Windows Forms de .NET Framework a .NET Core para Windows.
author: Thraka
ms.author: adegeo
ms.date: 01/24/2020
ms.openlocfilehash: efa73428c816eddc00c62c2275d3457c92284388
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206133"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="68c39-103">Procedimiento para: Migrar una aplicación de escritorio de Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="68c39-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="68c39-104">En este artículo se explica cómo migrar una aplicación de escritorio basada en Windows Forms de .NET Framework a .NET Core 3.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="68c39-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0 or later.</span></span> <span data-ttu-id="68c39-105">El SDK de .NET Core 3.0 incluye compatibilidad para las aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="68c39-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="68c39-106">Windows Forms sigue siendo un marco de solo Windows y solo se ejecuta en Windows.</span><span class="sxs-lookup"><span data-stu-id="68c39-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="68c39-107">En este ejemplo se usa la CLI del SDK de .NET Core para crear y administrar un proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="68c39-108">En este artículo, se usan diferentes nombres para identificar los tipos de archivos que se utilizan para la migración.</span><span class="sxs-lookup"><span data-stu-id="68c39-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="68c39-109">Al migrar su proyecto, sus archivos se nombrarán de manera diferente, así que establezca una relación mental con los que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="68c39-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="68c39-110">Archivo</span><span class="sxs-lookup"><span data-stu-id="68c39-110">File</span></span> | <span data-ttu-id="68c39-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c39-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="68c39-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="68c39-112">**MyApps.sln**</span></span> | <span data-ttu-id="68c39-113">Nombre del archivo de la solución.</span><span class="sxs-lookup"><span data-stu-id="68c39-113">The name of the solution file.</span></span> |
| <span data-ttu-id="68c39-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="68c39-114">**MyForms.csproj**</span></span> | <span data-ttu-id="68c39-115">Nombre del proyecto de Windows Forms de .NET Framework para migrar.</span><span class="sxs-lookup"><span data-stu-id="68c39-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="68c39-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="68c39-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="68c39-117">Nombre del nuevo proyecto de .NET Core que crea.</span><span class="sxs-lookup"><span data-stu-id="68c39-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="68c39-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="68c39-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="68c39-119">Ejecutable de la aplicación de Windows Forms de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="68c39-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="68c39-120">Prerequisites</span></span>

- <span data-ttu-id="68c39-121">[Visual Studio 2019 16.5, versión preliminar 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) o una versión posterior para cualquier trabajo de diseñador que se quiera realizar.</span><span class="sxs-lookup"><span data-stu-id="68c39-121">[Visual Studio 2019 16.5 Preview 1](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&ch=pre&rel=16) or later for any designer work you want to do.</span></span> <span data-ttu-id="68c39-122">Se recomienda actualizar a la [versión preliminar de Visual Studio](https://visualstudio.microsoft.com/vs/preview/) más reciente.</span><span class="sxs-lookup"><span data-stu-id="68c39-122">We recommend to update to the latest [Preview version of Visual Studio](https://visualstudio.microsoft.com/vs/preview/).</span></span>

  <span data-ttu-id="68c39-123">Instale las cargas de trabajo de Visual Studio siguientes:</span><span class="sxs-lookup"><span data-stu-id="68c39-123">Install the following Visual Studio workloads:</span></span>
  
  - <span data-ttu-id="68c39-124">Desarrollo de escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="68c39-124">.NET desktop development</span></span>
  - <span data-ttu-id="68c39-125">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="68c39-125">.NET Core cross-platform development</span></span>

- <span data-ttu-id="68c39-126">Un proyecto de Windows Forms en funcionamiento en una solución que se construye y ejecuta sin problemas.</span><span class="sxs-lookup"><span data-stu-id="68c39-126">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="68c39-127">Un proyecto codificado en C#.</span><span class="sxs-lookup"><span data-stu-id="68c39-127">A project coded in C#.</span></span>

> [!NOTE]
> <span data-ttu-id="68c39-128">Los proyectos de .NET Core 3.0 solo se admiten en **Visual Studio 2019** o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="68c39-128">.NET Core 3.0 projects are only supported in **Visual Studio 2019** or a later version.</span></span> <span data-ttu-id="68c39-129">A partir de **Visual Studio 2019 16.5, versión preliminar 1**, también se admite el diseñador de Windows Forms de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-129">Starting with **Visual Studio 2019 version 16.5 Preview 1**, the .NET Core Windows Forms designer is also supported.</span></span>
>
> <span data-ttu-id="68c39-130">Para habilitar el diseñador, vaya a **Herramientas** > **Opciones** > **Entorno** > **Características de vista previa** y seleccione la opción **Usar la versión preliminar del diseñador de Windows Forms del para aplicaciones .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="68c39-130">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

### <a name="consider"></a><span data-ttu-id="68c39-131">Tenga en cuenta que:</span><span class="sxs-lookup"><span data-stu-id="68c39-131">Consider</span></span>

<span data-ttu-id="68c39-132">Al migrar una aplicación de Windows Forms de .NET Framework, hay algunas cosas que debe tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="68c39-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="68c39-133">Compruebe que la aplicación cumple los requisitos para la migración.</span><span class="sxs-lookup"><span data-stu-id="68c39-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="68c39-134">Use el [analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para determinar si el proyecto se migrará a .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c39-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="68c39-135">Si el proyecto tiene problemas con .NET Core 3.0, el analizador le ayuda a identificar esos problemas.</span><span class="sxs-lookup"><span data-stu-id="68c39-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="68c39-136">Está usando una versión diferente de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="68c39-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="68c39-137">Cuando se publicó .NET Core 3.0 (versión preliminar 1), Windows Forms se puso a disposición de los usuarios en código abierto en GitHub.</span><span class="sxs-lookup"><span data-stu-id="68c39-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="68c39-138">El código para Windows Forms de .NET Core es una bifurcación del código base de Windows Forms de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="68c39-139">Es posible que existan algunas diferencias y la aplicación no se migre.</span><span class="sxs-lookup"><span data-stu-id="68c39-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="68c39-140">El [paquete de compatibilidad de Windows][compat-pack] puede ayudarle con la migración.</span><span class="sxs-lookup"><span data-stu-id="68c39-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="68c39-141">Algunas API que están disponibles en .NET Framework no están disponibles en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c39-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="68c39-142">El [paquete de compatibilidad de Windows][compat-pack] agrega muchas de estas API y puede ayudar a que su aplicación de Windows Forms sea compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="68c39-143">Actualice los paquetes de NuGet utilizados por el proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="68c39-144">Siempre se recomienda usar las últimas versiones de los paquetes de NuGet antes de cualquier migración.</span><span class="sxs-lookup"><span data-stu-id="68c39-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="68c39-145">Si la aplicación hace referencia a cualquier paquete de NuGet, actualícelo a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="68c39-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="68c39-146">Asegúrese de que la aplicación se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="68c39-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="68c39-147">Tras la actualización, si se han producido errores en el paquete, cambie el paquete a la versión más reciente que no rompa el código.</span><span class="sxs-lookup"><span data-stu-id="68c39-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="68c39-148">Creación de un nuevo proyecto de SDK</span><span class="sxs-lookup"><span data-stu-id="68c39-148">Create a new SDK project</span></span>

<span data-ttu-id="68c39-149">El nuevo proyecto .NET Core 3.0 que cree debe estar en un directorio diferente de su proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-149">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="68c39-150">Si ambos están en el mismo directorio, es posible que tenga conflictos con los archivos que se generan en el directorio **obj**.</span><span class="sxs-lookup"><span data-stu-id="68c39-150">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="68c39-151">En este ejemplo, vamos a crear un directorio denominado **MyFormsAppCore** en el directorio **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="68c39-151">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="68c39-152">A continuación, deberá crear el proyecto **MyFormsCore.csproj** en el directorio **MyFormsAppCore**.</span><span class="sxs-lookup"><span data-stu-id="68c39-152">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="68c39-153">Puede crear este archivo manualmente utilizando el editor de texto que prefiera.</span><span class="sxs-lookup"><span data-stu-id="68c39-153">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="68c39-154">Pegue el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="68c39-154">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="68c39-155">Si no desea crear manualmente el archivo de proyecto, puede usar Visual Studio o el SDK de .NET Core para generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-155">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="68c39-156">Sin embargo, debe eliminar todos los demás archivos generados por la plantilla de proyecto, excepto el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-156">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="68c39-157">Para usar el SDK, ejecute el siguiente comando desde el directorio **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="68c39-157">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="68c39-158">Después de crear **MyFormsCore.csproj**, la estructura de directorios debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="68c39-158">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="68c39-159">Agregue el proyecto **MyFormsCore.csproj** a **MyApps.sln** con Visual Studio o la CLI de .NET Core desde el directorio **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="68c39-159">Add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="68c39-160">Corrección de la generación de información de ensamblado</span><span class="sxs-lookup"><span data-stu-id="68c39-160">Fix assembly info generation</span></span>

<span data-ttu-id="68c39-161">Los proyectos de Windows Forms que se crearon con .NET Framework incluyen un archivo `AssemblyInfo.cs`, que contiene los atributos de ensamblado, como la versión del ensamblado que se generará.</span><span class="sxs-lookup"><span data-stu-id="68c39-161">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="68c39-162">Los proyectos de estilo SDK generan automáticamente esta información basándose en el archivo de proyecto de SDK.</span><span class="sxs-lookup"><span data-stu-id="68c39-162">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="68c39-163">Tener ambos tipos de "información de ensamblado" crea un conflicto.</span><span class="sxs-lookup"><span data-stu-id="68c39-163">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="68c39-164">Resuelva este problema deshabilitando la generación automática, lo que obliga al proyecto a usar su archivo `AssemblyInfo.cs` existente.</span><span class="sxs-lookup"><span data-stu-id="68c39-164">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="68c39-165">Hay tres opciones para agregar al nodo `<PropertyGroup>` principal.</span><span class="sxs-lookup"><span data-stu-id="68c39-165">There are three settings to add to the main `<PropertyGroup>` node.</span></span>

- <span data-ttu-id="68c39-166">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="68c39-166">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="68c39-167">Al establecer esta propiedad en `false`, no se generan los atributos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="68c39-167">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="68c39-168">Esto evita el conflicto con el archivo `AssemblyInfo.cs` existente en el proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-168">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="68c39-169">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="68c39-169">**AssemblyName**</span></span>\
<span data-ttu-id="68c39-170">El valor de esta propiedad es el binario de salida que se crea al compilar.</span><span class="sxs-lookup"><span data-stu-id="68c39-170">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="68c39-171">El nombre no necesita una extensión agregada.</span><span class="sxs-lookup"><span data-stu-id="68c39-171">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="68c39-172">Por ejemplo, el uso de `MyCoreApp` genera `MyCoreApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="68c39-172">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="68c39-173">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="68c39-173">**RootNamespace**</span></span>\
<span data-ttu-id="68c39-174">El espacio de nombres predeterminado que utiliza el proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-174">The default namespace used by your project.</span></span> <span data-ttu-id="68c39-175">Debe coincidir con el espacio de nombres predeterminado del proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-175">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="68c39-176">Agregue estos tres elementos al nodo `<PropertyGroup>` en el archivo `MyFormsCore.csproj`:</span><span class="sxs-lookup"><span data-stu-id="68c39-176">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="68c39-177">Adición de código fuente</span><span class="sxs-lookup"><span data-stu-id="68c39-177">Add source code</span></span>

<span data-ttu-id="68c39-178">Ahora, el proyecto **MyFormsCore.csproj** no compila ningún código.</span><span class="sxs-lookup"><span data-stu-id="68c39-178">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="68c39-179">De forma predeterminada, los proyectos de .NET Core incluyen automáticamente todo el código fuente en el directorio actual y los directorios secundarios.</span><span class="sxs-lookup"><span data-stu-id="68c39-179">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="68c39-180">Debe configurar el proyecto para incluir código del proyecto de .NET Framework con una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="68c39-180">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="68c39-181">Si el proyecto de .NET Framework usa archivos **.resx** para los iconos y los recursos de los formularios, deberá incluirlos también.</span><span class="sxs-lookup"><span data-stu-id="68c39-181">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span>

<span data-ttu-id="68c39-182">Agregue el siguiente nodo `<ItemGroup>` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-182">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="68c39-183">Cada instrucción incluye un patrón global de archivo que incluye los directorios secundarios.</span><span class="sxs-lookup"><span data-stu-id="68c39-183">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="68c39-184">Como alternativa, puede crear una entrada `<Compile>` o `<EmbeddedResource>` para cada archivo en el proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-184">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="68c39-185">Adición de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="68c39-185">Add NuGet packages</span></span>

<span data-ttu-id="68c39-186">Agregue cada paquete NuGet al que hace referencia el proyecto de .NET Framework al proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-186">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span>

<span data-ttu-id="68c39-187">Lo más probable es que su aplicación de Windows Forms de .NET Framework tenga un archivo **packages.config** que contenga una lista de todos los paquetes de NuGet a los que hace referencia su proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-187">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="68c39-188">Puede buscar en esta lista para determinar qué paquetes de NuGet se agregarán al proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-188">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="68c39-189">Por ejemplo, si el proyecto de .NET Framework hizo referencia a los paquetes de NuGet `MetroFramework`, `MetroFramework.Design` y `MetroFramework.Fonts`, agregue cada uno al proyecto con Visual Studio o la CLI de .NET Core del directorio **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="68c39-189">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="68c39-190">Los comandos anteriores podrían agregar las siguientes referencias de NuGet al proyecto **MyFormsCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="68c39-190">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="68c39-191">Migración de bibliotecas de controles</span><span class="sxs-lookup"><span data-stu-id="68c39-191">Port control libraries</span></span>

<span data-ttu-id="68c39-192">Si tiene un proyecto de biblioteca de controles de Windows Forms para migrar, las instrucciones son las mismas que para migrar un proyecto de aplicación de Windows Forms de .NET Framework, excepto algunas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="68c39-192">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="68c39-193">Y, en lugar de compilar en un archivo ejecutable, se compila en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="68c39-193">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="68c39-194">La diferencia entre el proyecto ejecutable y el proyecto de biblioteca, además de las rutas de acceso para los patrones globales de archivo que incluyen el código fuente, es mínima.</span><span class="sxs-lookup"><span data-stu-id="68c39-194">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="68c39-195">Usando el ejemplo del paso anterior, vamos a expandir los proyectos y archivos con los que estamos trabajando.</span><span class="sxs-lookup"><span data-stu-id="68c39-195">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="68c39-196">Archivo</span><span class="sxs-lookup"><span data-stu-id="68c39-196">File</span></span> | <span data-ttu-id="68c39-197">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c39-197">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="68c39-198">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="68c39-198">**MyApps.sln**</span></span> | <span data-ttu-id="68c39-199">Nombre del archivo de la solución.</span><span class="sxs-lookup"><span data-stu-id="68c39-199">The name of the solution file.</span></span> |
| <span data-ttu-id="68c39-200">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="68c39-200">**MyControls.csproj**</span></span> | <span data-ttu-id="68c39-201">Nombre del proyecto de controles de Windows Forms de .NET Framework para migrar.</span><span class="sxs-lookup"><span data-stu-id="68c39-201">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="68c39-202">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="68c39-202">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="68c39-203">Nombre del nuevo proyecto de biblioteca de .NET Core que crea.</span><span class="sxs-lookup"><span data-stu-id="68c39-203">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="68c39-204">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="68c39-204">**MyCoreControls.dll**</span></span> | <span data-ttu-id="68c39-205">La biblioteca de controles de Windows Forms de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-205">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="68c39-206">Tenga en cuenta las diferencias entre el proyecto `MyControlsCore.csproj` y el proyecto `MyFormsCore.csproj` creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="68c39-206">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="68c39-207">Este es un ejemplo del aspecto que podría tener el archivo de proyecto de biblioteca de controles de Windows Forms de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="68c39-207">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="68c39-208">Como puede ver, se quitó el nodo `<OutputType>`, que establece el compilador de forma predeterminada para generar una biblioteca en lugar de un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="68c39-208">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="68c39-209">`<AssemblyName>` y `<RootNamespace>` se han cambiado.</span><span class="sxs-lookup"><span data-stu-id="68c39-209">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="68c39-210">En concreto, `<RootNamespace>` debe coincidir con el espacio de nombres de la biblioteca de controles de Windows Forms que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="68c39-210">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="68c39-211">Y, finalmente, los nodos `<Compile>` y `<EmbeddedResource>` se ajustaron para apuntar a la carpeta de la biblioteca de controles de Windows Forms que está migrando.</span><span class="sxs-lookup"><span data-stu-id="68c39-211">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="68c39-212">A continuación, en el proyecto principal **MyFormsCore.csproj** de .NET Core, agregue una referencia a la nueva biblioteca de controles de Windows Forms de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-212">Next, in the main .NET Core **MyFormsCore.csproj** project, add a reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="68c39-213">Agregue una referencia con Visual Studio o la CLI de .NET Core desde el directorio **SolutionFolder**:</span><span class="sxs-lookup"><span data-stu-id="68c39-213">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="68c39-214">El comando anterior agrega lo siguiente al proyecto **MyFormsCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="68c39-214">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a><span data-ttu-id="68c39-215">Problemas de compilación</span><span class="sxs-lookup"><span data-stu-id="68c39-215">Compilation problems</span></span>

<span data-ttu-id="68c39-216">Si tiene problemas al compilar los proyectos, puede que esté usando algunas API solo de Windows que están disponibles en .NET Framework, pero no en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-216">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="68c39-217">Puede intentar agregar el paquete de NuGet del [paquete de compatibilidad de Windows][compat-pack] al proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c39-217">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="68c39-218">Este paquete solo se ejecuta en Windows y agrega aproximadamente 20 000 API de Windows a los proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="68c39-218">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="68c39-219">El comando anterior agrega lo siguiente al proyecto **MyFormsCore.csproj**:</span><span class="sxs-lookup"><span data-stu-id="68c39-219">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="68c39-220">Diseñador de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68c39-220">Windows Forms Designer</span></span>

<span data-ttu-id="68c39-221">Como se detalla en este artículo, Visual Studio 2019 solo admite el Diseñador de Forms en los proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-221">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="68c39-222">Mediante la creación de un proyecto de .NET Core en paralelo, puede probar el proyecto con .NET Core mientras utiliza el proyecto de .NET Framework para diseñar formularios.</span><span class="sxs-lookup"><span data-stu-id="68c39-222">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="68c39-223">El archivo de solución incluye proyectos de .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-223">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="68c39-224">Agregue y diseñe sus formularios y controles en el proyecto de .NET Framework, y en función de los patrones globales de archivos que agreguemos a los proyectos de .NET Core, cualquier archivo nuevo o modificado se incluirá automáticamente en los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-224">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="68c39-225">Una vez que Visual Studio 2019 sea compatible con el Diseñador de Windows Forms, podrá copiar/pegar el contenido de su archivo de proyecto de .NET Core en el archivo de proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68c39-225">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="68c39-226">A continuación, elimine los patrones globales de archivo agregados con los elementos `<Source>` y `<EmbeddedResource>`.</span><span class="sxs-lookup"><span data-stu-id="68c39-226">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="68c39-227">Corrija las rutas a cualquier referencia de proyecto utilizada por su aplicación.</span><span class="sxs-lookup"><span data-stu-id="68c39-227">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="68c39-228">Esto actualiza eficazmente el proyecto de .NET Framework a un proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-228">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68c39-229">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="68c39-229">Next steps</span></span>

- <span data-ttu-id="68c39-230">Obtenga información sobre los [Cambios importantes para la migración de .NET Framework a .NET Core](../compatibility/fx-core.md).</span><span class="sxs-lookup"><span data-stu-id="68c39-230">Learn about [breaking changes from .NET Framework to .NET Core](../compatibility/fx-core.md).</span></span>
- <span data-ttu-id="68c39-231">Obtenga más información sobre el [paquete de compatibilidad de Windows][compat-pack].</span><span class="sxs-lookup"><span data-stu-id="68c39-231">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="68c39-232">Vea un [vídeo sobre cómo migrar](https://www.youtube.com/watch?v=upVQEUc_KwU) el proyecto de Windows Forms de .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c39-232">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
