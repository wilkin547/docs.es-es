---
title: Controlar y generar excepciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 82e314dacc9fb2657a3a7088a928b59d00282a5d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="995ac-102">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="995ac-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="995ac-103">Las aplicaciones tienen que ser capaces de controlar de forma coherente los errores que se producen durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="995ac-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="995ac-104">.NET proporciona un modelo para notificar errores a las aplicaciones de manera uniforme: las operaciones .NET indican errores iniciando excepciones.</span><span class="sxs-lookup"><span data-stu-id="995ac-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="995ac-105">Excepciones</span><span class="sxs-lookup"><span data-stu-id="995ac-105">Exceptions</span></span>

<span data-ttu-id="995ac-106">Una excepción es cualquier condición de error o comportamiento inesperado que encuentra un programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="995ac-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="995ac-107">Las excepciones pueden iniciarse debido a un error en el código propio o en el código al que se llama (por ejemplo, una biblioteca compartida), a recursos del sistema operativo no disponibles, a condiciones inesperadas que encuentra el runtime (por ejemplo, imposibilidad de comprobar el código), etc.</span><span class="sxs-lookup"><span data-stu-id="995ac-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="995ac-108">La aplicación puede recuperarse de algunas de estas condiciones, pero no de todas.</span><span class="sxs-lookup"><span data-stu-id="995ac-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="995ac-109">Aunque es posible recuperarse de la mayoría de las excepciones que se producen en la aplicación, no ocurre lo mismo con las excepciones de runtime.</span><span class="sxs-lookup"><span data-stu-id="995ac-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="995ac-110">En .NET, una excepción es un objeto que hereda de la clase <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="995ac-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="995ac-111">Una excepción se inicia desde un área del código en la que ha producido un problema.</span><span class="sxs-lookup"><span data-stu-id="995ac-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="995ac-112">La excepción se pasa hacia arriba en la pila hasta que la aplicación la controla o el programa finaliza.</span><span class="sxs-lookup"><span data-stu-id="995ac-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="995ac-113">Excepciones vs. métodos tradicionales de control de errores</span><span class="sxs-lookup"><span data-stu-id="995ac-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="995ac-114">Tradicionalmente, el modelo de control de errores de un lenguaje se basaba en el modo exclusivo del lenguaje de detectar los errores y buscarles controladores, o bien en el mecanismo de control de errores ofrecido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="995ac-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="995ac-115">La forma en que .NET implementa el control de excepciones proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="995ac-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="995ac-116">La administración e iniciación de excepciones funciona de igual modo para los lenguajes de programación. NET.</span><span class="sxs-lookup"><span data-stu-id="995ac-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="995ac-117">No requiere ninguna sintaxis de lenguaje específica para controlar las excepciones, pero permite que cada lenguaje defina su propia sintaxis.</span><span class="sxs-lookup"><span data-stu-id="995ac-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="995ac-118">Las excepciones pueden iniciarse en varios procesos en incluso límites de máquina.</span><span class="sxs-lookup"><span data-stu-id="995ac-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="995ac-119">Se puede agregar el código de control de excepciones a una aplicación para aumentar la confiabilidad del programa.</span><span class="sxs-lookup"><span data-stu-id="995ac-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="995ac-120">Las excepciones ofrecen ventajas sobre otros métodos de notificación de errores, por ejemplo, los códigos de retorno.</span><span class="sxs-lookup"><span data-stu-id="995ac-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="995ac-121">Lo errores no pasan desapercibidos porque si se inicia una excepción y no la controla, el runtime finaliza la aplicación.</span><span class="sxs-lookup"><span data-stu-id="995ac-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="995ac-122">Los valores no válidos no continúan propagándose por el sistema como resultado de que el código no pueda encontrar un código de retorno de error.</span><span class="sxs-lookup"><span data-stu-id="995ac-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="995ac-123">Excepciones comunes</span><span class="sxs-lookup"><span data-stu-id="995ac-123">Common Exceptions</span></span>

<span data-ttu-id="995ac-124">En la tabla siguiente se muestra algunas excepciones comunes con ejemplos de las causas que las originan.</span><span class="sxs-lookup"><span data-stu-id="995ac-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="995ac-125">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="995ac-125">Exception type</span></span> | <span data-ttu-id="995ac-126">Tipo base</span><span class="sxs-lookup"><span data-stu-id="995ac-126">Base type</span></span> | <span data-ttu-id="995ac-127">Description</span><span class="sxs-lookup"><span data-stu-id="995ac-127">Description</span></span> | <span data-ttu-id="995ac-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="995ac-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| <xref:System.Exception> | <xref:System.Object> | <span data-ttu-id="995ac-129">Clase base de todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="995ac-129">Base class for all exceptions.</span></span> | <span data-ttu-id="995ac-130">Ninguno (utilice una clase derivada de esta excepción).</span><span class="sxs-lookup"><span data-stu-id="995ac-130">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="995ac-131">El tiempo de ejecución la genera solo cuando una matriz no está correctamente indexada.</span><span class="sxs-lookup"><span data-stu-id="995ac-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="995ac-132">La indexación de una matriz fuera de su intervalo válido: `arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="995ac-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| <xref:System.NullReferenceException> | <xref:System.Exception> | <span data-ttu-id="995ac-133">El tiempo de ejecución la genera solo cuando se hace referencia a un objeto null.</span><span class="sxs-lookup"><span data-stu-id="995ac-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| <xref:System.InvalidOperationException> | <xref:System.Exception> | <span data-ttu-id="995ac-134">Los métodos la generan si se produce un estado no válido.</span><span class="sxs-lookup"><span data-stu-id="995ac-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="995ac-135">Llamada a `Enumerator.GetNext()` después de quitar un elemento de la colección subyacente.</span><span class="sxs-lookup"><span data-stu-id="995ac-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <xref:System.Exception> | <span data-ttu-id="995ac-136">Clase base de todas las excepciones de argumento.</span><span class="sxs-lookup"><span data-stu-id="995ac-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="995ac-137">Ninguno (utilice una clase derivada de esta excepción).</span><span class="sxs-lookup"><span data-stu-id="995ac-137">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <xref:System.Exception> | <span data-ttu-id="995ac-138">Los métodos que no permiten que un argumento sea null la generan.</span><span class="sxs-lookup"><span data-stu-id="995ac-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| <xref:System.ArgumentOutOfRangeException> | <xref:System.Exception> | <span data-ttu-id="995ac-139">Los métodos que comprueban que los argumentos se encuentran en un intervalo determinado la generan.</span><span class="sxs-lookup"><span data-stu-id="995ac-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="995ac-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="995ac-140">See Also</span></span>

* [<span data-ttu-id="995ac-141">Clase Exception y propiedades</span><span class="sxs-lookup"><span data-stu-id="995ac-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="995ac-142">Utilizar el bloque Try/Catch para detectar excepciones</span><span class="sxs-lookup"><span data-stu-id="995ac-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="995ac-143">Cómo: Utilizar excepciones específicas en un bloque Catch</span><span class="sxs-lookup"><span data-stu-id="995ac-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="995ac-144">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="995ac-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="995ac-145">Cómo crear excepciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="995ac-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="995ac-146">Utilizar controladores de excepciones filtradas por el usuario</span><span class="sxs-lookup"><span data-stu-id="995ac-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="995ac-147">Utilizar bloques Finally</span><span class="sxs-lookup"><span data-stu-id="995ac-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="995ac-148">Controlar excepciones de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="995ac-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="995ac-149">Procedimientos recomendados para excepciones</span><span class="sxs-lookup"><span data-stu-id="995ac-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="995ac-150">Para obtener más información acerca de cómo funcionan las excepciones en. NET, consulte [Qué deben saber los desarrolladores sobre las excepciones en runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="995ac-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>
