---
title: Exposición de los componentes de .NET Core a COM
description: En este tutorial se muestra cómo exponer una clase a COM desde .NET Core. Generaremos automáticamente un servidor COM y un manifiesto de servidor en paralelo para COM sin registro.
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 17d85b9e9734fae0bb69f94da8c08669216ab0ae
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242873"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="9878d-104">Exposición de los componentes de .NET Core a COM</span><span class="sxs-lookup"><span data-stu-id="9878d-104">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="9878d-105">En .NET Core, el proceso de exposición de los objetos .NET a COM se ha simplificado significativamente en comparación con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9878d-105">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="9878d-106">El siguiente proceso le guiará a través de la exposición de una clase a COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-106">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="9878d-107">En este tutorial se le enseñará a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9878d-107">This tutorial shows you how to:</span></span>

- <span data-ttu-id="9878d-108">Exponer una clase a COM desde .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9878d-108">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="9878d-109">Generar un servidor COM como parte de la creación de la biblioteca de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9878d-109">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="9878d-110">Generar automáticamente un manifiesto de servidor en paralelo para COM sin registro.</span><span class="sxs-lookup"><span data-stu-id="9878d-110">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9878d-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9878d-111">Prerequisites</span></span>

- <span data-ttu-id="9878d-112">Instale el [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download) o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="9878d-112">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="9878d-113">Crear la biblioteca</span><span class="sxs-lookup"><span data-stu-id="9878d-113">Create the library</span></span>

<span data-ttu-id="9878d-114">El primer paso consiste en crear la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9878d-114">The first step is to create the library.</span></span>

1. <span data-ttu-id="9878d-115">Cree una carpeta nueva y, en ella, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9878d-115">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="9878d-116">Abra `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="9878d-116">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="9878d-117">Agregue `using System.Runtime.InteropServices;` a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="9878d-117">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="9878d-118">Cree una interfaz denominada `IServer`.</span><span class="sxs-lookup"><span data-stu-id="9878d-118">Create an interface named `IServer`.</span></span> <span data-ttu-id="9878d-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9878d-119">For example:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   [ComVisible(true)]
   [Guid(ContractGuids.ServerInterface)]
   [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
   public interface IServer
   {
       /// <summary>
       /// Compute the value of the constant Pi.
       /// </summary>
       double ComputePi();
   }
   ```

5. <span data-ttu-id="9878d-120">Agregue el atributo `[Guid("<IID>")]` a la interfaz con el GUID de la interfaz para la interfaz COM que está implementando.</span><span class="sxs-lookup"><span data-stu-id="9878d-120">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="9878d-121">Por ejemplo: `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="9878d-121">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="9878d-122">Tenga en cuenta que este GUID debe ser único, ya que es el único identificador de esta interfaz para COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-122">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="9878d-123">En Visual Studio, puede generar un GUID desde Herramientas > Crear GUID para abrir la herramienta de creación de GUID.</span><span class="sxs-lookup"><span data-stu-id="9878d-123">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="9878d-124">Agregue el atributo `[InterfaceType]` a la interfaz y especifique qué interfaces COM base debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="9878d-124">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="9878d-125">Cree una clase denominada `Server` que implemente `IServer`.</span><span class="sxs-lookup"><span data-stu-id="9878d-125">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="9878d-126">Agregue el atributo `[Guid("<CLSID>")]` a la clase, con el identificador de clase GUID para la clase COM que está implementando.</span><span class="sxs-lookup"><span data-stu-id="9878d-126">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="9878d-127">Por ejemplo: `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="9878d-127">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="9878d-128">Igual que sucede con la interfaz GUID, este GUID debe ser único, ya que es el único identificador de esta interfaz para COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-128">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="9878d-129">Agregue el atributo `[ComVisible(true)]` a la interfaz y a la clase.</span><span class="sxs-lookup"><span data-stu-id="9878d-129">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9878d-130">A diferencia de lo que ocurre en .NET Framework, en .NET Core debe especificar el CLSID de cualquier clase que le interese que se pueda activar mediante COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-130">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="9878d-131">Generar el host de COM</span><span class="sxs-lookup"><span data-stu-id="9878d-131">Generate the COM host</span></span>

1. <span data-ttu-id="9878d-132">Abra el archivo de proyecto `.csproj` y agregue `<EnableComHosting>true</EnableComHosting>` en una etiqueta `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="9878d-132">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="9878d-133">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9878d-133">Build the project.</span></span>

<span data-ttu-id="9878d-134">El resultado contendrá un archivo `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` y `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="9878d-134">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="9878d-135">Registrar el host COM para COM</span><span class="sxs-lookup"><span data-stu-id="9878d-135">Register the COM host for COM</span></span>

<span data-ttu-id="9878d-136">Abra un símbolo del sistema con privilegios elevados y ejecute `regsvr32 ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="9878d-136">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="9878d-137">Esto registrará todos los objetos .NET expuestos con COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-137">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="9878d-138">Habilitar RegFree COM</span><span class="sxs-lookup"><span data-stu-id="9878d-138">Enabling RegFree COM</span></span>

1. <span data-ttu-id="9878d-139">Abra el archivo de proyecto `.csproj` y agregue `<EnableRegFreeCom>true</EnableRegFreeCom>` en una etiqueta `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="9878d-139">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="9878d-140">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9878d-140">Build the project.</span></span>

<span data-ttu-id="9878d-141">Ahora el resultado también contendrá un archivo `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="9878d-141">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="9878d-142">Este archivo es el manifiesto en paralelo que se podrá usar con COM sin registro.</span><span class="sxs-lookup"><span data-stu-id="9878d-142">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="9878d-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9878d-143">Sample</span></span>

<span data-ttu-id="9878d-144">Puede encontrar un [ejemplo de servidor COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) totalmente funcional en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="9878d-144">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="9878d-145">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="9878d-145">Additional notes</span></span>

<span data-ttu-id="9878d-146">A diferencia de lo que ocurre en .NET Framework, .NET Core no admite la generación de una biblioteca de tipos COM (TLB) a partir de un ensamblado de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9878d-146">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="9878d-147">La instrucción es escribir manualmente un archivo IDL o un encabezado C/C++ para las declaraciones nativas de las interfaces COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-147">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="9878d-148">No se admiten [implementaciones autocontenidas](../deploying/index.md#publish-self-contained) de componentes COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-148">[Self-contained deployments](../deploying/index.md#publish-self-contained) of COM components are not supported.</span></span> <span data-ttu-id="9878d-149">Solo se admiten las [implementaciones dependientes del runtime](../deploying/index.md#publish-runtime-dependent) de los componentes COM.</span><span class="sxs-lookup"><span data-stu-id="9878d-149">Only [runtime-dependent deployments](../deploying/index.md#publish-runtime-dependent) of COM components are supported.</span></span>

<span data-ttu-id="9878d-150">Además, la carga de .NET Framework y .NET Core en el mismo proceso presenta limitaciones de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9878d-150">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="9878d-151">La limitación principal es la depuración de componentes administrados, ya que no es posible depurar .NET Framework y .NET Core al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9878d-151">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="9878d-152">Asimismo, las dos instancias en tiempo de ejecución no comparten ensamblados administrados.</span><span class="sxs-lookup"><span data-stu-id="9878d-152">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="9878d-153">Esto significa que no es posible compartir tipos de .NET reales entre los dos tiempos de ejecución, por lo que todas las interacciones deben restringirse a los contratos de interfaz COM expuestos.</span><span class="sxs-lookup"><span data-stu-id="9878d-153">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
