---
title: Identificar funciones en archivos DLL
description: Identifique funciones en archivos DLL. La identidad de una función DLL se compone de un nombre de función o un ordinal, y el nombre del archivo DLL en el que se puede encontrar la implementación.
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
ms.openlocfilehash: b1d95329e9b8ac6cd1f8ffc3111a50b6ab010462
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281721"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="c5385-104">Identificar funciones en archivos DLL</span><span class="sxs-lookup"><span data-stu-id="c5385-104">Identifying Functions in DLLs</span></span>

<span data-ttu-id="c5385-105">La identidad de una función DLL consta de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c5385-105">The identity of a DLL function consists of the following elements:</span></span>  
  
- <span data-ttu-id="c5385-106">Nombre de la función u ordinal</span><span class="sxs-lookup"><span data-stu-id="c5385-106">Function name or ordinal</span></span>  
  
- <span data-ttu-id="c5385-107">Nombre del archivo DLL en el que se puede encontrar la implementación</span><span class="sxs-lookup"><span data-stu-id="c5385-107">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="c5385-108">Por ejemplo, si se especifica la función **MessageBox** en el archivo User32.dll se identifica la función (**MessageBox**) y su ubicación (User32.dll, User32 o user32).</span><span class="sxs-lookup"><span data-stu-id="c5385-108">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="c5385-109">La interfaz de programación de aplicaciones de Microsoft Windows (API de Windows) puede contener dos versiones de cada función que controla caracteres y cadenas: una versión ANSI de caracteres de un byte y una versión Unicode de caracteres de dos bytes.</span><span class="sxs-lookup"><span data-stu-id="c5385-109">The Microsoft Windows application programming interface (Windows API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="c5385-110">Si no se especifica, el juego de caracteres (representado por el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>) es ANSI de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5385-110">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="c5385-111">Algunas funciones pueden tener más de dos versiones.</span><span class="sxs-lookup"><span data-stu-id="c5385-111">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="c5385-112">**MessageBoxA** es el punto de entrada ANSI para la función **MessageBox**; **MessageBoxW** es la versión de Unicode.</span><span class="sxs-lookup"><span data-stu-id="c5385-112">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="c5385-113">Puede enumerar los nombres de función de un archivo DLL específico, como user32.dll, mediante la ejecución de una variedad de herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5385-113">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="c5385-114">Por ejemplo, puede usar `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` para obtener los nombres de función.</span><span class="sxs-lookup"><span data-stu-id="c5385-114">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="c5385-115">Puede cambiar el nombre de una función no administrada por el nombre que quiera dentro del código siempre que se asigne el nombre nuevo al punto de entrada original en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="c5385-115">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="c5385-116">Para obtener instrucciones sobre cómo cambiar el nombre de una función DLL no administrada en código fuente administrado, vea [Especificar un punto de entrada](specifying-an-entry-point.md).</span><span class="sxs-lookup"><span data-stu-id="c5385-116">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="c5385-117">La invocación de plataforma permite controlar una parte importante del sistema operativo mediante la llamada a las funciones de la API de Windows y otros archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="c5385-117">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Windows API and other DLLs.</span></span> <span data-ttu-id="c5385-118">Además de la API de Windows, hay muchas otras API y archivos DLL disponibles a través de la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="c5385-118">In addition to the Windows API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="c5385-119">En la tabla siguiente se describen varios archivos DLL que se usan habitualmente en la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="c5385-119">The following table describes several commonly used DLLs in the Windows API.</span></span>  
  
|<span data-ttu-id="c5385-120">Archivo DLL</span><span class="sxs-lookup"><span data-stu-id="c5385-120">DLL</span></span>|<span data-ttu-id="c5385-121">Descripción del contenido</span><span class="sxs-lookup"><span data-stu-id="c5385-121">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="c5385-122">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="c5385-122">GDI32.dll</span></span>|<span data-ttu-id="c5385-123">Funciones de Interfaz de dispositivo gráfico (GDI) para salida de dispositivos, como las de dibujo y administración de fuentes.</span><span class="sxs-lookup"><span data-stu-id="c5385-123">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="c5385-124">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="c5385-124">Kernel32.dll</span></span>|<span data-ttu-id="c5385-125">Funciones de bajo nivel del sistema operativo para la administración de memoria y el control de recursos.</span><span class="sxs-lookup"><span data-stu-id="c5385-125">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="c5385-126">User32.dll</span><span class="sxs-lookup"><span data-stu-id="c5385-126">User32.dll</span></span>|<span data-ttu-id="c5385-127">Funciones de administración de Windows para el control de mensajes, temporizadores, menús y comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="c5385-127">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="c5385-128">Para obtener la documentación completa sobre la API de Windows, vea el SDK de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="c5385-128">For complete documentation on the Windows API, see the Platform SDK.</span></span> <span data-ttu-id="c5385-129">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="c5385-129">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5385-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5385-130">See also</span></span>

- [<span data-ttu-id="c5385-131">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="c5385-131">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="c5385-132">Especificar un punto de entrada</span><span class="sxs-lookup"><span data-stu-id="c5385-132">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="c5385-133">Creación de una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="c5385-133">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="c5385-134">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="c5385-134">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="c5385-135">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="c5385-135">Calling a DLL Function</span></span>](calling-a-dll-function.md)
