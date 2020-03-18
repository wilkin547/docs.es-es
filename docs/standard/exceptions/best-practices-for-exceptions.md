---
title: Procedimientos recomendados para excepciones - .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 1de231b01e3fa97e78a87ae6b0595a9b5536374e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160175"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="2fc40-102">Procedimientos recomendados para excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-102">Best practices for exceptions</span></span>

<span data-ttu-id="2fc40-103">Una aplicación diseñada correctamente controla las excepciones y los errores para evitar que se bloquee.</span><span class="sxs-lookup"><span data-stu-id="2fc40-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="2fc40-104">En este artículo se describen los procedimientos recomendados para controlar y crear excepciones.</span><span class="sxs-lookup"><span data-stu-id="2fc40-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a><span data-ttu-id="2fc40-105">Uso de bloques try/catch/finally para recuperarse de errores o liberar recursos</span><span class="sxs-lookup"><span data-stu-id="2fc40-105">Use try/catch/finally blocks to recover from errors or release resources</span></span>

<span data-ttu-id="2fc40-106">Use bloques `try`/`catch` alrededor del código que podría generar una excepción ***y*** su código podrá recuperarse de una excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-106">Use `try`/`catch` blocks around code that can potentially generate an exception ***and*** your code can recover from that exception.</span></span> <span data-ttu-id="2fc40-107">Ordene siempre las excepciones de los bloques `catch` de la más derivada a la menos.</span><span class="sxs-lookup"><span data-stu-id="2fc40-107">In `catch` blocks, always order exceptions from the most derived to the least derived.</span></span> <span data-ttu-id="2fc40-108">Todas las excepciones se derivan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-108">All exceptions derive from <xref:System.Exception>.</span></span> <span data-ttu-id="2fc40-109">Las excepciones más derivadas no las controla una cláusula catch que está precedida por una cláusula catch para una clase de excepción base.</span><span class="sxs-lookup"><span data-stu-id="2fc40-109">More derived exceptions are not handled by a catch clause that is preceded by a catch clause for a base exception class.</span></span> <span data-ttu-id="2fc40-110">Cuando el código no puede recuperarse de una excepción, no capture esa excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-110">When your code cannot recover from an exception, don't catch that exception.</span></span> <span data-ttu-id="2fc40-111">Habilite los métodos más arriba en la pila de llamadas para recuperarse si es posible.</span><span class="sxs-lookup"><span data-stu-id="2fc40-111">Enable methods further up the call stack to recover if possible.</span></span>

<span data-ttu-id="2fc40-112">Limpie los recursos asignados con instrucciones `using` o bloques `finally`.</span><span class="sxs-lookup"><span data-stu-id="2fc40-112">Clean up resources allocated with either `using` statements, or `finally` blocks.</span></span> <span data-ttu-id="2fc40-113">Dé prioridad a las instrucciones `using` para limpiar automáticamente los recursos cuando se produzcan excepciones.</span><span class="sxs-lookup"><span data-stu-id="2fc40-113">Prefer `using` statements to automatically clean up resources when exceptions are thrown.</span></span> <span data-ttu-id="2fc40-114">Use bloques `finally` para limpiar los recursos que no implementan <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-114">Use `finally` blocks to clean up resources that don't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="2fc40-115">El código de una cláusula `finally` casi siempre se ejecuta incluso cuando se producen excepciones.</span><span class="sxs-lookup"><span data-stu-id="2fc40-115">Code in a `finally` clause is almost always executed even when exceptions are thrown.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="2fc40-116">Administrar condiciones comunes sin iniciar excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-116">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="2fc40-117">Para las condiciones con probabilidad de producirse, pero que podrían desencadenar una excepción, considere la posibilidad de controlarlas de forma que se evite la excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-117">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="2fc40-118">Por ejemplo, si intenta se cerrar una conexión que ya está cerrada, obtendrá `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="2fc40-118">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="2fc40-119">Se puede evitar mediante una instrucción `if` para comprobar el estado de conexión antes de intentar cerrarla.</span><span class="sxs-lookup"><span data-stu-id="2fc40-119">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

<span data-ttu-id="2fc40-120">Si no comprueba el estado de la conexión antes de cerrar, se puede detectar la excepción `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="2fc40-120">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

<span data-ttu-id="2fc40-121">El método que se elija depende de la frecuencia con la que espera que se produzca el evento.</span><span class="sxs-lookup"><span data-stu-id="2fc40-121">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="2fc40-122">Utilice el control de excepciones si el evento no se produce con frecuencia, es decir, si el evento es muy excepcional e indica un error (como un final de archivo inesperado).</span><span class="sxs-lookup"><span data-stu-id="2fc40-122">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="2fc40-123">Cuando se usa el control de excepciones, se ejecuta menos código en condiciones normales.</span><span class="sxs-lookup"><span data-stu-id="2fc40-123">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="2fc40-124">Compruebe condiciones de error en el código cuando el evento se produce con frecuencia y se puede considerar como parte de la ejecución normal.</span><span class="sxs-lookup"><span data-stu-id="2fc40-124">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="2fc40-125">Cuando se buscan condiciones de error comunes, se ejecuta menos código porque se evitan excepciones.</span><span class="sxs-lookup"><span data-stu-id="2fc40-125">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="2fc40-126">Diseñar clases para que se puedan evitar excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-126">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="2fc40-127">Una clase puede proporcionar métodos o propiedades que permiten evitar realizar una llamada que desencadenaría una excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-127">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="2fc40-128">Por ejemplo, una clase <xref:System.IO.FileStream> proporciona métodos que ayudan a determinar si se ha alcanzado el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="2fc40-128">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="2fc40-129">Esto se puede usar para evitar la excepción que se inicia si se lee más allá del final del archivo.</span><span class="sxs-lookup"><span data-stu-id="2fc40-129">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="2fc40-130">En el ejemplo siguiente se muestra cómo leer hasta el final de un archivo sin desencadenar una excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-130">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

<span data-ttu-id="2fc40-131">Otro modo de evitar excepciones es devolver un valor NULL (o el valor predeterminado) para los casos de errores muy frecuentes en lugar de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-131">Another way to avoid exceptions is to return null (or default) for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="2fc40-132">Un caso de error muy común se puede considerar como un flujo de control normal.</span><span class="sxs-lookup"><span data-stu-id="2fc40-132">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="2fc40-133">Al devolver un valor NULL en estos casos, se minimiza el impacto en el rendimiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2fc40-133">By returning null (or default) in these cases, you minimize the performance impact to an app.</span></span>

<span data-ttu-id="2fc40-134">Para los tipos de valores, el uso de `Nullable<T>` o de valores predeterminados como indicador de error es algo que se debe tener en cuenta para la aplicación en particular.</span><span class="sxs-lookup"><span data-stu-id="2fc40-134">For value types, whether to use `Nullable<T>` or default as your error indicator is something to consider for your particular app.</span></span> <span data-ttu-id="2fc40-135">Al utilizar `Nullable<Guid>`, `default` se convierte en `null` en lugar de `Guid.Empty`.</span><span class="sxs-lookup"><span data-stu-id="2fc40-135">By using `Nullable<Guid>`, `default` becomes `null` instead of `Guid.Empty`.</span></span> <span data-ttu-id="2fc40-136">Algunas veces, agregar `Nullable<T>` puede aclarar cuando un valor está presente o ausente.</span><span class="sxs-lookup"><span data-stu-id="2fc40-136">Some times, adding `Nullable<T>` can make it clearer when a value is present or absent.</span></span> <span data-ttu-id="2fc40-137">Otras veces, agregar `Nullable<T>` puede crear casos adicionales para comprobar que no son necesarios, y solo sirven para crear posibles orígenes de errores.</span><span class="sxs-lookup"><span data-stu-id="2fc40-137">Other times, adding `Nullable<T>` can create extra cases to check that aren't necessary, and only serve to create potential sources of errors.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="2fc40-138">Iniciar excepciones en lugar de devolver un código de error</span><span class="sxs-lookup"><span data-stu-id="2fc40-138">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="2fc40-139">Las excepciones garantizan que los errores no pasen desapercibidos porque la llamada al código no compruebe un código de retorno.</span><span class="sxs-lookup"><span data-stu-id="2fc40-139">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span>

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="2fc40-140">Uso de los tipos de excepción predefinidos de .NET</span><span class="sxs-lookup"><span data-stu-id="2fc40-140">Use the predefined .NET exception types</span></span>

<span data-ttu-id="2fc40-141">Solo se deben introducir nuevas clases de excepción si no se puede aplicar ningún tipo predefinido.</span><span class="sxs-lookup"><span data-stu-id="2fc40-141">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="2fc40-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2fc40-142">For example:</span></span>

- <span data-ttu-id="2fc40-143">Inicie una excepción <xref:System.InvalidOperationException> si un conjunto de propiedades o una llamada a un método no resultan apropiados de acuerdo con el estado actual del objeto.</span><span class="sxs-lookup"><span data-stu-id="2fc40-143">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="2fc40-144">Inicie una excepción <xref:System.ArgumentException> o una de las clases predefinidas que derivan de <xref:System.ArgumentException> si se pasan parámetros no válidos.</span><span class="sxs-lookup"><span data-stu-id="2fc40-144">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="2fc40-145">Termine los nombres de clases de excepción con la palabra `Exception`</span><span class="sxs-lookup"><span data-stu-id="2fc40-145">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="2fc40-146">Cuando se necesite una excepción personalizada, debe ponerse el nombre apropiado y derivarla de la clase <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-146">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="2fc40-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2fc40-147">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="2fc40-148">Incluir tres constructores en las clases de excepciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="2fc40-148">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="2fc40-149">Use al menos tres constructores comunes al crear sus propias clases de excepción: el constructor sin parámetros, un constructor que tome un mensaje de cadena y un constructor que tome un mensaje de cadena y una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="2fc40-149">Use at least the three common constructors when creating your own exception classes: the parameterless constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

- <span data-ttu-id="2fc40-150"><xref:System.Exception.%23ctor>, que utiliza valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2fc40-150"><xref:System.Exception.%23ctor>, which uses default values.</span></span>

- <span data-ttu-id="2fc40-151"><xref:System.Exception.%23ctor%28System.String%29>, que acepta un mensaje de cadena.</span><span class="sxs-lookup"><span data-stu-id="2fc40-151"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>

- <span data-ttu-id="2fc40-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, que acepta un mensaje de cadena y una excepción interna.</span><span class="sxs-lookup"><span data-stu-id="2fc40-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>

<span data-ttu-id="2fc40-153">Por ejemplo, consulte [Cómo: Crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2fc40-153">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="2fc40-154">Asegúrese de que los datos de excepción estén disponibles cuando el código se ejecute de forma remota</span><span class="sxs-lookup"><span data-stu-id="2fc40-154">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="2fc40-155">Cuando cree excepciones definidas por el usuario, debe garantizar que los metadatos de las excepciones están disponibles para el código que se ejecute de forma remota.</span><span class="sxs-lookup"><span data-stu-id="2fc40-155">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span>

<span data-ttu-id="2fc40-156">Por ejemplo, en las implementaciones de .NET que admiten los dominios de aplicación, pueden producirse excepciones entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2fc40-156">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="2fc40-157">Por ejemplo, supongamos que el dominio de aplicación A crea el dominio de aplicación B, que ejecuta código que inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-157">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="2fc40-158">Para que el dominio de aplicación A detecte y controle la excepción correctamente, debe poder encontrar el ensamblado que contiene la excepción iniciada por el dominio de aplicación B. Si el dominio de aplicación B inicia una excepción contenida en un ensamblado en su base de aplicación pero no en la base de aplicación del dominio de aplicación A, el dominio de aplicación A no podrá encontrar la excepción y common language runtime iniciará una excepción de <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-158">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="2fc40-159">Para evitar esta situación, puede implementar el ensamblado que contiene la información de la excepción de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="2fc40-159">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="2fc40-160">Ponga el ensamblado en una base de aplicación compartida por los dos dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2fc40-160">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="2fc40-161">\- o -</span><span class="sxs-lookup"><span data-stu-id="2fc40-161">\- or -</span></span>

- <span data-ttu-id="2fc40-162">Si los dominios no comparten una base de aplicación común, firme el ensamblado que contiene la información de la excepción con un nombre seguro e impleméntelo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2fc40-162">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="2fc40-163">Usar mensajes de error gramaticalmente correctos</span><span class="sxs-lookup"><span data-stu-id="2fc40-163">Use grammatically correct error messages</span></span>

<span data-ttu-id="2fc40-164">Escriba frases claras e incluya puntuación final.</span><span class="sxs-lookup"><span data-stu-id="2fc40-164">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="2fc40-165">Todas las oraciones de la cadena asignada a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> deben terminar en punto.</span><span class="sxs-lookup"><span data-stu-id="2fc40-165">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="2fc40-166">Por ejemplo, "la tabla del registro se ha desbordado".</span><span class="sxs-lookup"><span data-stu-id="2fc40-166">For example, "The log table has overflowed."</span></span> <span data-ttu-id="2fc40-167">podría ser una cadena de mensaje adecuada.</span><span class="sxs-lookup"><span data-stu-id="2fc40-167">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="2fc40-168">Incluir un mensaje de cadena localizada en todas las excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-168">Include a localized string message in every exception</span></span>

<span data-ttu-id="2fc40-169">El mensaje de error que ve el usuario deriva de la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> de la excepción que se ha generado, y no del nombre de la clase de excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-169">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="2fc40-170">Normalmente, se asigna un valor a la propiedad <xref:System.Exception.Message?displayProperty=nameWithType> pasando la cadena de mensaje al argumento `message` de un [constructor de excepciones](xref:System.Exception.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="2fc40-170">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span>

<span data-ttu-id="2fc40-171">Para las aplicaciones localizadas, debe proporcionar una cadena de mensaje localizada para todas las excepciones que la aplicación pueda desencadenar.</span><span class="sxs-lookup"><span data-stu-id="2fc40-171">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="2fc40-172">Use archivos de recursos para proporcionar mensajes de error localizados.</span><span class="sxs-lookup"><span data-stu-id="2fc40-172">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="2fc40-173">Para información sobre la localización de aplicaciones y la recuperación de cadenas localizadas, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="2fc40-173">For information on localizing applications and retrieving localized strings, see the following articles:</span></span>

- [<span data-ttu-id="2fc40-174">Procedimientos: Creación de excepciones definidas por el usuario con mensajes de excepción localizados</span><span class="sxs-lookup"><span data-stu-id="2fc40-174">How to: create user-defined exceptions with localized exception messages</span></span>](how-to-create-localized-exception-messages.md)
- [<span data-ttu-id="2fc40-175">Recursos de aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="2fc40-175">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="2fc40-176">En excepciones personalizadas, proporcione propiedades adicionales según sea necesario</span><span class="sxs-lookup"><span data-stu-id="2fc40-176">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="2fc40-177">Únicamente proporcione información adicional para una excepción, además de la cadena del mensaje personalizado, si hay un escenario de programación en el que dicha información sea útil.</span><span class="sxs-lookup"><span data-stu-id="2fc40-177">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="2fc40-178">Por ejemplo, <xref:System.IO.FileNotFoundException> proporciona la propiedad <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-178">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="2fc40-179">Colocar instrucciones de iniciación para que el seguimiento de la pila sea útil</span><span class="sxs-lookup"><span data-stu-id="2fc40-179">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="2fc40-180">El seguimiento de pila comienza en la instrucción en que se produce la excepción y termina en la instrucción `catch` que detecta la excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-180">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="2fc40-181">Usar métodos de generador de excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-181">Use exception builder methods</span></span>

<span data-ttu-id="2fc40-182">Es habitual que una clase produzca la misma excepción desde distintos lugares de su implementación.</span><span class="sxs-lookup"><span data-stu-id="2fc40-182">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="2fc40-183">Para evitar el exceso de código, use métodos del asistente que creen la excepción y la devuelvan.</span><span class="sxs-lookup"><span data-stu-id="2fc40-183">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="2fc40-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2fc40-184">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

<span data-ttu-id="2fc40-185">En algunos casos, es más apropiado usar el constructor de excepciones para generar la excepción.</span><span class="sxs-lookup"><span data-stu-id="2fc40-185">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="2fc40-186">Un ejemplo es una clase de excepción global, como <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-186">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a><span data-ttu-id="2fc40-187">Restauración del estado cuando los métodos no se completan debido a excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-187">Restore state when methods don't complete due to exceptions</span></span>

<span data-ttu-id="2fc40-188">Los autores de llamadas deben poder asumir que no se producen efectos no deseados cuando se produce una excepción desde un método.</span><span class="sxs-lookup"><span data-stu-id="2fc40-188">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="2fc40-189">Por ejemplo, si tiene código que transfiere dinero mediante la retirada de una cuenta y el depósito en otra, y se inicia una excepción mientras se ejecuta el depósito, no quiere que la retirada siga siendo efectiva.</span><span class="sxs-lookup"><span data-stu-id="2fc40-189">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

<span data-ttu-id="2fc40-190">El método anterior no produce ninguna excepción directamente, pero debe escribirse de forma defensiva para que, si se produce un error en la operación de depósito, se invierta la retirada.</span><span class="sxs-lookup"><span data-stu-id="2fc40-190">The method above does not directly throw any exceptions, but must be written defensively so that if the deposit operation fails, the withdrawal is reversed.</span></span>

<span data-ttu-id="2fc40-191">Para controlar esta situación se puede detectar cualquier excepción iniciada por la transacción del depósito y revertir la retirada.</span><span class="sxs-lookup"><span data-stu-id="2fc40-191">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

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

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

<span data-ttu-id="2fc40-192">Este ejemplo muestra el uso de `throw` para volver a iniciar la excepción original, que puede facilitar a los autores de llamada ver la causa del problema real sin tener que examinar la propiedad <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="2fc40-192">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="2fc40-193">Como alternativa se puede iniciar una nueva excepción e incluir la excepción original como excepción interna:</span><span class="sxs-lookup"><span data-stu-id="2fc40-193">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a><span data-ttu-id="2fc40-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fc40-194">See also</span></span>

- [<span data-ttu-id="2fc40-195">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2fc40-195">Exceptions</span></span>](index.md)
