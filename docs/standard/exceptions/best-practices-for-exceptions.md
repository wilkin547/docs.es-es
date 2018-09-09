---
title: Procedimientos recomendados para excepciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee61d01acbf9c409eaedc04ff3e949908e1d595e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225141"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="c9328-102">Procedimientos recomendados para excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-102">Best practices for exceptions</span></span>

<span data-ttu-id="c9328-103">Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee.</span><span class="sxs-lookup"><span data-stu-id="c9328-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="c9328-104">En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.</span><span class="sxs-lookup"><span data-stu-id="c9328-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks"></a><span data-ttu-id="c9328-105">Uso de bloques Try/Catch/Finally</span><span class="sxs-lookup"><span data-stu-id="c9328-105">Use try/catch/finally blocks</span></span>

<span data-ttu-id="c9328-106">Use bloques de código `try`/`catch`/`finally` que podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-106">Use `try`/`catch`/`finally` blocks around code that can potentially generate an exception.</span></span> 

<span data-ttu-id="c9328-107">Ordene siempre las excepciones de los bloques `catch` de la más específica a la menos.</span><span class="sxs-lookup"><span data-stu-id="c9328-107">In `catch` blocks, always order exceptions from the most specific to the least specific.</span></span>

<span data-ttu-id="c9328-108">Use un bloque `finally` para limpiar los recursos, tanto si puede recuperarlos como si no.</span><span class="sxs-lookup"><span data-stu-id="c9328-108">Use a `finally` block to clean up resources, whether you can recover or not.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="c9328-109">Administrar condiciones comunes sin iniciar excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-109">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="c9328-110">Para las condiciones con probabilidad de producirse, pero que podrían desencadenar una excepción, considere la posibilidad de controlarlas de forma que se evite la excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-110">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="c9328-111">Por ejemplo, si intenta se cerrar una conexión que ya está cerrada, obtendrá `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="c9328-111">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="c9328-112">Se puede evitar mediante una instrucción `if` para comprobar el estado de conexión antes de intentar cerrarla.</span><span class="sxs-lookup"><span data-stu-id="c9328-112">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

<span data-ttu-id="c9328-113">Si no comprueba el estado de la conexión antes de cerrar, se puede detectar la excepción `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="c9328-113">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

<span data-ttu-id="c9328-114">El método que se elija depende de la frecuencia con la que espera que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="c9328-114">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="c9328-115">Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error (como un final de archivo inesperado).</span><span class="sxs-lookup"><span data-stu-id="c9328-115">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="c9328-116">Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.</span><span class="sxs-lookup"><span data-stu-id="c9328-116">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="c9328-117">Compruebe condiciones de error en el código cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal.</span><span class="sxs-lookup"><span data-stu-id="c9328-117">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="c9328-118">Cuando se buscan condiciones de error comunes, se ejecuta menos código porque se evitan excepciones.</span><span class="sxs-lookup"><span data-stu-id="c9328-118">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="c9328-119">Diseñar clases para que se puedan evitar excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-119">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="c9328-120">Una clase puede proporcionar métodos o propiedades que permiten evitar realizar una llamada que desencadenaría una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-120">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="c9328-121">Por ejemplo, una clase <xref:System.IO.FileStream> proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="c9328-121">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="c9328-122">Esto se puede usar para evitar la excepción que se inicia si se lee más allá del final del archivo.</span><span class="sxs-lookup"><span data-stu-id="c9328-122">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="c9328-123">En el ejemplo siguiente se muestra cómo leer hasta el final de un archivo sin desencadenar una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-123">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

<span data-ttu-id="c9328-124">Otro modo de evitar excepciones es devolver NULL para los casos de errores muy frecuentes en lugar de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-124">Another way to avoid exceptions is to return null for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="c9328-125">Un caso de error muy común se puede considerar como un flujo de control normal.</span><span class="sxs-lookup"><span data-stu-id="c9328-125">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="c9328-126">Al devolver un valor null en estos casos, se minimiza el impacto en el rendimiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c9328-126">By returning null in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="c9328-127">Iniciar excepciones en lugar de devolver un código de error</span><span class="sxs-lookup"><span data-stu-id="c9328-127">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="c9328-128">Las excepciones garantizan que los errores no pasen desapercibidos porque la llamada al código no compruebe un código de retorno.</span><span class="sxs-lookup"><span data-stu-id="c9328-128">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span> 

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="c9328-129">Uso de los tipos de excepción predefinidos de .NET</span><span class="sxs-lookup"><span data-stu-id="c9328-129">Use the predefined .NET exception types</span></span>

<span data-ttu-id="c9328-130">Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido.</span><span class="sxs-lookup"><span data-stu-id="c9328-130">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="c9328-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9328-131">For example:</span></span>

- <span data-ttu-id="c9328-132">Inicie una excepción <xref:System.InvalidOperationException> si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.</span><span class="sxs-lookup"><span data-stu-id="c9328-132">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="c9328-133">Inicie una excepción <xref:System.ArgumentException> o una de las clases predefinidas que derivan de <xref:System.ArgumentException> si se pasan parámetros no válidos.</span><span class="sxs-lookup"><span data-stu-id="c9328-133">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="c9328-134">Termine los nombres de clases de excepción con la palabra `Exception`</span><span class="sxs-lookup"><span data-stu-id="c9328-134">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="c9328-135">Cuando se necesite una excepción personalizada, debe ponerse el nombre apropiado y derivarla de la clase <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="c9328-135">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="c9328-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9328-136">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="c9328-137">Incluir tres constructores en las clases de excepciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c9328-137">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="c9328-138">Use al menos tres constructores comunes al crear sus propias clases de excepción: el constructor predeterminado, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="c9328-138">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="c9328-139"><xref:System.Exception.%23ctor>, que utiliza valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c9328-139"><xref:System.Exception.%23ctor>, which uses default values.</span></span>
  
* <span data-ttu-id="c9328-140"><xref:System.Exception.%23ctor%28System.String%29>, que acepta un mensaje de cadena.</span><span class="sxs-lookup"><span data-stu-id="c9328-140"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>  
  
* <span data-ttu-id="c9328-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, que acepta un mensaje de cadena y una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="c9328-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>  
  
<span data-ttu-id="c9328-142">Por ejemplo, consulte [Cómo: Crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="c9328-142">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="c9328-143">Asegúrese de que los datos de excepción estén disponibles cuando el código se ejecute de forma remota</span><span class="sxs-lookup"><span data-stu-id="c9328-143">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="c9328-144">Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota.</span><span class="sxs-lookup"><span data-stu-id="c9328-144">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span> 

<span data-ttu-id="c9328-145">Por ejemplo, en las implementaciones de .NET que admiten los dominios de aplicación, pueden producirse excepciones entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c9328-145">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="c9328-146">Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-146">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="c9328-147">Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción iniciada por el dominio de aplicación B. Si el dominio de aplicación B inicia una excepción contenida en un ensamblado en su base de aplicación pero no en la base de aplicación del dominio de aplicación A, el dominio de aplicación A no podrá encontrar la excepción y common language runtime iniciará una excepción de <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="c9328-147">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="c9328-148">Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="c9328-148">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="c9328-149">Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c9328-149">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="c9328-150">\- o -</span><span class="sxs-lookup"><span data-stu-id="c9328-150">\- or -</span></span>

- <span data-ttu-id="c9328-151">Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c9328-151">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="c9328-152">Usar mensajes de error gramaticalmente correctos</span><span class="sxs-lookup"><span data-stu-id="c9328-152">Use grammatically correct error messages</span></span>

<span data-ttu-id="c9328-153">Escriba frases claras e incluya puntuación final.</span><span class="sxs-lookup"><span data-stu-id="c9328-153">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="c9328-154">Todas las oraciones de la cadena asignada a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> deben terminar en punto.</span><span class="sxs-lookup"><span data-stu-id="c9328-154">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="c9328-155">Por ejemplo, "la tabla del registro se ha desbordado".</span><span class="sxs-lookup"><span data-stu-id="c9328-155">For example, "The log table has overflowed."</span></span> <span data-ttu-id="c9328-156">podría ser una cadena de mensaje adecuada.</span><span class="sxs-lookup"><span data-stu-id="c9328-156">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="c9328-157">Incluir un mensaje de cadena localizada en todas las excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-157">Include a localized string message in every exception</span></span>

<span data-ttu-id="c9328-158">El mensaje de error que ve el usuario deriva de la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> de la excepción que se ha generado, y no del nombre de la clase de excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-158">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="c9328-159">Normalmente, se asigna un valor a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> pasando la cadena de mensaje al argumento `message` de un [constructor de excepciones](xref:System.Exception.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="c9328-159">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span> 

<span data-ttu-id="c9328-160">Para las aplicaciones localizadas, debe proporcionar una cadena de mensaje localizada para todas las excepciones que la aplicación pueda desencadenar.</span><span class="sxs-lookup"><span data-stu-id="c9328-160">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="c9328-161">Use archivos de recursos para proporcionar mensajes de error localizados.</span><span class="sxs-lookup"><span data-stu-id="c9328-161">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="c9328-162">Para obtener información sobre la localización de aplicaciones y la recuperación de cadenas localizadas, vea [Recursos de aplicaciones de escritorio](../../framework/resources/index.md) y <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c9328-162">For information on localizing applications and retrieving localized strings, see [Resources in Desktop Apps](../../framework/resources/index.md) and <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="c9328-163">En excepciones personalizadas, proporcione propiedades adicionales según sea necesario</span><span class="sxs-lookup"><span data-stu-id="c9328-163">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="c9328-164">Únicamente proporcione información adicional para una excepción, además de la cadena del mensaje personalizado, si hay un escenario de programación en el que dicha información sea útil.</span><span class="sxs-lookup"><span data-stu-id="c9328-164">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="c9328-165">Por ejemplo, <xref:System.IO.FileNotFoundException> proporciona la propiedad <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="c9328-165">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="c9328-166">Colocar instrucciones de iniciación para que el seguimiento de la pila sea útil</span><span class="sxs-lookup"><span data-stu-id="c9328-166">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="c9328-167">El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-167">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="c9328-168">Usar métodos de generador de excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-168">Use exception builder methods</span></span>

<span data-ttu-id="c9328-169">Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación.</span><span class="sxs-lookup"><span data-stu-id="c9328-169">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="c9328-170">Para evitar el exceso de código, use métodos auxiliares que creen la excepción y la devuelvan.</span><span class="sxs-lookup"><span data-stu-id="c9328-170">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="c9328-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9328-171">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
<span data-ttu-id="c9328-172">En algunos casos, es más apropiado usar el constructor de excepciones para generar la excepción.</span><span class="sxs-lookup"><span data-stu-id="c9328-172">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="c9328-173">Un ejemplo es una clase de excepción global, como <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="c9328-173">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a><span data-ttu-id="c9328-174">Eliminar los resultados intermedios cuando se inicie una excepción</span><span class="sxs-lookup"><span data-stu-id="c9328-174">Clean up intermediate results when throwing an exception</span></span>

<span data-ttu-id="c9328-175">Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método.</span><span class="sxs-lookup"><span data-stu-id="c9328-175">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="c9328-176">Por ejemplo, si tiene código que transfiere dinero mediante la retirada de una cuenta y el depósito en otra, y se inicia una excepción mientras se ejecuta el depósito, no quiere que la retirada siga siendo efectiva.</span><span class="sxs-lookup"><span data-stu-id="c9328-176">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

<span data-ttu-id="c9328-177">Para controlar esta situación se puede detectar cualquier excepción iniciada por la transacción del depósito y revertir la retirada.</span><span class="sxs-lookup"><span data-stu-id="c9328-177">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

<span data-ttu-id="c9328-178">Este ejemplo muestra el uso de `throw` para volver a iniciar la excepción original, que puede facilitar a los autores de llamada ver la causa del problema real sin tener que examinar la propiedad <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="c9328-178">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="c9328-179">Como alternativa se puede iniciar una nueva excepción e incluir la excepción original como excepción interna:</span><span class="sxs-lookup"><span data-stu-id="c9328-179">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a><span data-ttu-id="c9328-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9328-180">See also</span></span>

- [<span data-ttu-id="c9328-181">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c9328-181">Exceptions</span></span>](index.md)
