---
title: Exposición de los componentes de .NET Core a COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 686d1b31478121a8b2c907d99672a5fcc3438a71
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849034"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="b5ced-102">Exposición de los componentes de .NET Core a COM</span><span class="sxs-lookup"><span data-stu-id="b5ced-102">Exposing .NET Core Components to COM</span></span>

<span data-ttu-id="b5ced-103">En .NET Core, el proceso de exposición de los objetos .NET a COM se ha simplificado significativamente en comparación con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5ced-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="b5ced-104">El siguiente proceso le guiará a través de la exposición de una clase a COM.</span><span class="sxs-lookup"><span data-stu-id="b5ced-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="b5ced-105">En este tutorial se le enseñará a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5ced-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="b5ced-106">Exponer una clase a COM desde .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b5ced-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="b5ced-107">Generar un servidor COM como parte de la creación de la biblioteca de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b5ced-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="b5ced-108">Generar automáticamente un manifiesto de servidor en paralelo para COM sin registro.</span><span class="sxs-lookup"><span data-stu-id="b5ced-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5ced-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5ced-109">Prerequisites</span></span>

- <span data-ttu-id="b5ced-110">Instale el [SDK de la versión preliminar 7 de .NET Core 3.0](https://dotnet.microsoft.com/download) o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="b5ced-110">Install the [.NET Core 3.0 Preview 7 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="b5ced-111">Crear la biblioteca</span><span class="sxs-lookup"><span data-stu-id="b5ced-111">Create the library</span></span>

<span data-ttu-id="b5ced-112">El primer paso consiste en crear la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b5ced-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="b5ced-113">Cree una carpeta y, en ella, ejecute `dotnet new classlib`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-113">Create a new folder, and in that folder run `dotnet new classlib`.</span></span>
2. <span data-ttu-id="b5ced-114">Abra `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="b5ced-115">Agregue `using System.Runtime.InteropServices;` a la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="b5ced-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="b5ced-116">Cree una interfaz denominada `IServer`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="b5ced-117">Por ejemplo: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]</span><span class="sxs-lookup"><span data-stu-id="b5ced-117">For example: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]</span></span>
5. <span data-ttu-id="b5ced-118">Agregue el atributo `[Guid("<IID>")]` a la interfaz con el GUID de la interfaz para la interfaz COM que está implementando.</span><span class="sxs-lookup"><span data-stu-id="b5ced-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="b5ced-119">Por ejemplo: `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="b5ced-120">Tenga en cuenta que este GUID debe ser único, ya que es el único identificador de esta interfaz para COM.</span><span class="sxs-lookup"><span data-stu-id="b5ced-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="b5ced-121">En Visual Studio, puede generar un GUID desde Herramientas > Crear GUID para abrir la herramienta de creación de GUID.</span><span class="sxs-lookup"><span data-stu-id="b5ced-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="b5ced-122">Agregue el atributo `[InterfaceType]` a la interfaz y especifique qué interfaces COM base debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b5ced-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="b5ced-123">Cree una clase denominada `Server` que implemente `IServer`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="b5ced-124">Agregue el atributo `[Guid("<CLSID>")]` a la clase, con el identificador de clase GUID para la clase COM que está implementando.</span><span class="sxs-lookup"><span data-stu-id="b5ced-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="b5ced-125">Por ejemplo: `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="b5ced-126">Igual que sucede con la interfaz GUID, este GUID debe ser único, ya que es el único identificador de esta interfaz para COM.</span><span class="sxs-lookup"><span data-stu-id="b5ced-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="b5ced-127">Agregue el atributo `[ComVisible(true)]` a la interfaz y a la clase.</span><span class="sxs-lookup"><span data-stu-id="b5ced-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ced-128">A diferencia de lo que ocurre en .NET Framework, en .NET Core debe especificar el CLSID de cualquier clase que le interese que se pueda activar mediante COM.</span><span class="sxs-lookup"><span data-stu-id="b5ced-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="b5ced-129">Generar el host de COM</span><span class="sxs-lookup"><span data-stu-id="b5ced-129">Generate the COM host</span></span>

1. <span data-ttu-id="b5ced-130">Abra el archivo de proyecto `.csproj` y agregue `<EnableComHosting>true</EnableComHosting>` en una etiqueta `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="b5ced-131">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5ced-131">Build the project.</span></span>

<span data-ttu-id="b5ced-132">El resultado contendrá un archivo `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` y `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="b5ced-133">Registrar el host COM para COM</span><span class="sxs-lookup"><span data-stu-id="b5ced-133">Register the COM host for COM</span></span>

<span data-ttu-id="b5ced-134">Abra un símbolo del sistema con privilegios elevados y ejecute `regsvr32 ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="b5ced-135">Esto registrará todos los objetos .NET expuestos con COM.</span><span class="sxs-lookup"><span data-stu-id="b5ced-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="b5ced-136">Habilitar RegFree COM</span><span class="sxs-lookup"><span data-stu-id="b5ced-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="b5ced-137">Abra el archivo de proyecto `.csproj` y agregue `<EnableRegFreeCom>true</EnableRegFreeCom>` en una etiqueta `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="b5ced-138">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b5ced-138">Build the project.</span></span>

<span data-ttu-id="b5ced-139">Ahora el resultado también contendrá un archivo `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="b5ced-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="b5ced-140">Este archivo es el manifiesto en paralelo que se podrá usar con COM sin registro.</span><span class="sxs-lookup"><span data-stu-id="b5ced-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="b5ced-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5ced-141">Sample</span></span>

<span data-ttu-id="b5ced-142">Puede encontrar un [ejemplo de servidor COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) totalmente funcional en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="b5ced-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="b5ced-143">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="b5ced-143">Additional Notes</span></span>

<span data-ttu-id="b5ced-144">A diferencia de lo que ocurre en .NET Framework, .NET Core no admite la generación de una biblioteca de tipos COM (TLB) a partir de un ensamblado de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b5ced-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="b5ced-145">Tendrá que escribir manualmente un archivo IDL o un encabezado C++ para las declaraciones nativas de las interfaces.</span><span class="sxs-lookup"><span data-stu-id="b5ced-145">You will either have to manually write an IDL file or a C++ header for the native declarations of your interfaces.</span></span>

<span data-ttu-id="b5ced-146">Además, no se admite la carga de .NET Framework y .NET Core en el mismo proceso. Por lo tanto, no se admite la carga de un servidor COM de .NET Core en un proceso de cliente COM de .NET Framework o viceversa.</span><span class="sxs-lookup"><span data-stu-id="b5ced-146">Additionally, loading both .NET Framework and .NET Core into the same process is unsupported, and as a result loading a .NET Core COM server into a .NET Framework COM client process or vice versa is not supported.</span></span>
