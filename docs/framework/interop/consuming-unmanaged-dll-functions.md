---
title: Consumir funciones DLL no administradas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd1e5f4fc03da2310022efdeb4530440b5e07f3d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="aa8e0-102">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="aa8e0-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="aa8e0-103">La invocación de plataforma es un servicio que permite al código administrado llamar a funciones no administradas implementadas en bibliotecas de vínculos dinámicos (DLL), como los de la API Win32.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Win32 API.</span></span> <span data-ttu-id="aa8e0-104">Busca y llama a una función exportada y calcula las referencias de sus argumentos (enteros, cadenas, matrices, estructuras etc.) a través de los límites de interoperación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span> <span data-ttu-id="aa8e0-105">Para más información sobre este servicio, vea [Aproximación a la invocación de plataforma](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-105">For more information about this service, see [A Closer Look at Platform Invoke](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).</span></span>  
  
 <span data-ttu-id="aa8e0-106">En esta sección se presentan varias tareas asociadas con el consumo de funciones DLL no administradas.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-106">This section introduces several tasks associated with consuming unmanaged DLL functions.</span></span> <span data-ttu-id="aa8e0-107">Además de las tareas siguientes, hay consideraciones generales y un vínculo que proporciona más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-107">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="aa8e0-108">Para consumir funciones DLL exportadas</span><span class="sxs-lookup"><span data-stu-id="aa8e0-108">To consume exported DLL functions</span></span>  
  
1.  <span data-ttu-id="aa8e0-109">[Identificar funciones en archivos DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-109">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="aa8e0-110">Como mínimo, debe especificar el nombre de la función y el nombre del archivo DLL que la contiene.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-110">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2.  <span data-ttu-id="aa8e0-111">[Crear una clase para contener funciones de archivos DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-111">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="aa8e0-112">Puede usar una clase existente, crear una clase individual para cada función no administrada o crear una clase que contiene un conjunto de funciones no administradas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-112">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3.  <span data-ttu-id="aa8e0-113">[Crear prototipos en código administrado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-113">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="aa8e0-114">[Visual Basic] Use la instrucción **Declare** con las palabras clave **Function** y **Lib**.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-114">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="aa8e0-115">En algunos casos excepcionales, puede usar **DllImportAttribute** con las palabras clave **Shared Function**.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-115">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="aa8e0-116">Estos casos se explican más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-116">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="aa8e0-117">[C#] Use **DllImportAttribute** para identificar el archivo DLL y la función.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-117">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="aa8e0-118">Marque el método con los modificadores **static** y **extern**.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-118">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="aa8e0-119">[C++] Use **DllImportAttribute** para identificar el archivo DLL y la función.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-119">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="aa8e0-120">Marque la función o el método contenedor con **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-120">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4.  <span data-ttu-id="aa8e0-121">[Llamar a una función DLL](../../../docs/framework/interop/calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-121">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="aa8e0-122">Llame al método de la clase administrada como haría con cualquier otro método administrado.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-122">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="aa8e0-123">[Pasar estructuras](../../../docs/framework/interop/passing-structures.md) e [implementar funciones de devolución de llamada](../../../docs/framework/interop/callback-functions.md) son casos especiales.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-123">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="aa8e0-124">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="aa8e0-124">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="aa8e0-125">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="aa8e0-125">A closer look at platform invoke</span></span>  
 <span data-ttu-id="aa8e0-126">La invocación de plataforma usa metadatos para encontrar las funciones exportadas y calcular las referencias de sus argumentos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-126">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="aa8e0-127">En la siguiente ilustración se muestra este proceso.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-127">The following illustration shows this process.</span></span>  
  
 <span data-ttu-id="aa8e0-128">![Invocación de plataforma](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span><span class="sxs-lookup"><span data-stu-id="aa8e0-128">![Platform invoke](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")</span></span>  
<span data-ttu-id="aa8e0-129">Una invocación de plataforma llama a una función DLL no administrada</span><span class="sxs-lookup"><span data-stu-id="aa8e0-129">A platform invoke call to an unmanaged DLL function</span></span>  
  
 <span data-ttu-id="aa8e0-130">Cuando la invocación de plataforma llama a una función no administrada, realiza la siguiente secuencia de acciones:</span><span class="sxs-lookup"><span data-stu-id="aa8e0-130">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1.  <span data-ttu-id="aa8e0-131">Busca el archivo DLL que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-131">Locates the DLL containing the function.</span></span>  
  
2.  <span data-ttu-id="aa8e0-132">Carga el archivo DLL en la memoria.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-132">Loads the DLL into memory.</span></span>  
  
3.  <span data-ttu-id="aa8e0-133">Busca la dirección de la función en la memoria, inserta sus argumentos en la pila y calcula las referencias de los datos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-133">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa8e0-134">La búsqueda y carga del archivo DLL y la búsqueda de la dirección de la función en memoria solo se realiza en la primera llamada a la función.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-134">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4.  <span data-ttu-id="aa8e0-135">Transfiere el control a la función no administrada.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-135">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="aa8e0-136">La invocación de plataforma devuelve las excepciones generadas por la función no administrada al llamador administrado.</span><span class="sxs-lookup"><span data-stu-id="aa8e0-136">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8e0-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa8e0-137">See Also</span></span>  
 <span data-ttu-id="aa8e0-138">[Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="aa8e0-138">[Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)</span></span>  
 [<span data-ttu-id="aa8e0-139">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="aa8e0-139">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="aa8e0-140">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="aa8e0-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="aa8e0-141">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="aa8e0-141">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
