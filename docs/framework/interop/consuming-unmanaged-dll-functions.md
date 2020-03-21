---
title: Consumir funciones DLL no administradas
ms.date: 03/30/2017
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
ms.openlocfilehash: 7ec1f129dcc19300dd5a4e7c5e627d9e0edf29a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400954"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="2e48e-102">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="2e48e-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="2e48e-103">La invocación de plataforma es un servicio que permite al código administrado llamar a funciones no administradas implementadas en bibliotecas de vínculos dinámicos (DLL), como los de la API de Windows.</span><span class="sxs-lookup"><span data-stu-id="2e48e-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="2e48e-104">Busca y llama a una función exportada y calcula las referencias de sus argumentos (enteros, cadenas, matrices, estructuras etc.) a través de los límites de interoperación según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2e48e-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="2e48e-105">En esta sección se introducen las tareas asociadas con el consumo de funciones DLL no administradas y se proporciona más información sobre la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="2e48e-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="2e48e-106">Además de las tareas siguientes, hay consideraciones generales y un vínculo que proporciona más información y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2e48e-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="2e48e-107">Para consumir funciones DLL exportadas</span><span class="sxs-lookup"><span data-stu-id="2e48e-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="2e48e-108">[Identificar funciones en archivos DLL](identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="2e48e-108">[Identify functions in DLLs](identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="2e48e-109">Como mínimo, debe especificar el nombre de la función y el nombre del archivo DLL que la contiene.</span><span class="sxs-lookup"><span data-stu-id="2e48e-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="2e48e-110">[Crear una clase para contener funciones de archivos DLL](creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="2e48e-110">[Create a class to hold DLL functions](creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="2e48e-111">Puede usar una clase existente, crear una clase individual para cada función no administrada o crear una clase que contiene un conjunto de funciones no administradas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2e48e-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="2e48e-112">[Crear prototipos en código administrado](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="2e48e-112">[Create prototypes in managed code](creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="2e48e-113">[Visual Basic] Use la instrucción **Declare** con las palabras clave **Function** y **Lib**.</span><span class="sxs-lookup"><span data-stu-id="2e48e-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="2e48e-114">En algunos casos excepcionales, puede usar **DllImportAttribute** con las palabras clave **Shared Function**.</span><span class="sxs-lookup"><span data-stu-id="2e48e-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="2e48e-115">Estos casos se explican más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="2e48e-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="2e48e-116">[C-] Utilice **DllImportAttribute** para identificar el archivo DLL y la función.</span><span class="sxs-lookup"><span data-stu-id="2e48e-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="2e48e-117">Marque el método con los modificadores **static** y **extern**.</span><span class="sxs-lookup"><span data-stu-id="2e48e-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="2e48e-118">[C++] Use **DllImportAttribute** para identificar el archivo DLL y la función.</span><span class="sxs-lookup"><span data-stu-id="2e48e-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="2e48e-119">Marque la función o el método contenedor con **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="2e48e-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="2e48e-120">[Llamar a una función DLL](calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="2e48e-120">[Call a DLL function](calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="2e48e-121">Llame al método de la clase administrada como haría con cualquier otro método administrado.</span><span class="sxs-lookup"><span data-stu-id="2e48e-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="2e48e-122">[Pasar estructuras](passing-structures.md) e [implementar funciones de devolución de llamada](callback-functions.md) son casos especiales.</span><span class="sxs-lookup"><span data-stu-id="2e48e-122">[Passing structures](passing-structures.md) and [implementing callback functions](callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="2e48e-123">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="2e48e-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="2e48e-124">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="2e48e-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="2e48e-125">La invocación de plataforma usa metadatos para encontrar las funciones exportadas y serializar sus argumentos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e48e-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="2e48e-126">En la siguiente ilustración se muestra este proceso.</span><span class="sxs-lookup"><span data-stu-id="2e48e-126">The following illustration shows this process.</span></span>  
  
 ![Diagrama en el que se muestra una llamada de invocación de plataforma.](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="2e48e-128">Cuando la invocación de plataforma llama a una función no administrada, realiza la siguiente secuencia de acciones:</span><span class="sxs-lookup"><span data-stu-id="2e48e-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="2e48e-129">Busca el archivo DLL que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="2e48e-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="2e48e-130">Carga el archivo DLL en la memoria.</span><span class="sxs-lookup"><span data-stu-id="2e48e-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="2e48e-131">Busca la dirección de la función en la memoria, inserta sus argumentos en la pila y calcula las referencias de los datos si es necesario.</span><span class="sxs-lookup"><span data-stu-id="2e48e-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2e48e-132">La búsqueda y carga del archivo DLL y la búsqueda de la dirección de la función en memoria solo se realiza en la primera llamada a la función.</span><span class="sxs-lookup"><span data-stu-id="2e48e-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="2e48e-133">Transfiere el control a la función no administrada.</span><span class="sxs-lookup"><span data-stu-id="2e48e-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="2e48e-134">La invocación de plataforma devuelve las excepciones generadas por la función no administrada al llamador administrado.</span><span class="sxs-lookup"><span data-stu-id="2e48e-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e48e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e48e-135">See also</span></span>

- [<span data-ttu-id="2e48e-136">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="2e48e-136">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="2e48e-137">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="2e48e-137">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="2e48e-138">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2e48e-138">Interop Marshaling</span></span>](interop-marshaling.md)
