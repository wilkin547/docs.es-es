---
title: Usar tipos de excepciones estándar
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743544"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="42c7b-102">Usar tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="42c7b-102">Using Standard Exception Types</span></span>
<span data-ttu-id="42c7b-103">En esta sección se describen las excepciones estándar proporcionadas por el marco de trabajo y los detalles de su uso.</span><span class="sxs-lookup"><span data-stu-id="42c7b-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="42c7b-104">La lista no es exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="42c7b-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="42c7b-105">Consulte la documentación de referencia de .NET Framework para ver el uso de otros tipos de excepción de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="42c7b-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="42c7b-106">Excepción y SystemException</span><span class="sxs-lookup"><span data-stu-id="42c7b-106">Exception and SystemException</span></span>
 <span data-ttu-id="42c7b-107">❌ no inician <xref:System.Exception?displayProperty=nameWithType> ni <xref:System.SystemException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="42c7b-107">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="42c7b-108">❌ no detecta `System.Exception` ni `System.SystemException` en el código del marco de trabajo, a menos que pretenda volver a producirlo.</span><span class="sxs-lookup"><span data-stu-id="42c7b-108">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="42c7b-109">❌ evitar la detección de `System.Exception` o `System.SystemException`, excepto en los controladores de excepciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="42c7b-109">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="42c7b-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="42c7b-110">ApplicationException</span></span>
 <span data-ttu-id="42c7b-111">❌ no inician o derivan de <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="42c7b-111">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="42c7b-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="42c7b-112">InvalidOperationException</span></span>
 <span data-ttu-id="42c7b-113">✔️ iniciar una <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.</span><span class="sxs-lookup"><span data-stu-id="42c7b-113">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="42c7b-114">ArgumentException, ArgumentNullException y ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="42c7b-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="42c7b-115">✔️ inician <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos no válidos a un miembro.</span><span class="sxs-lookup"><span data-stu-id="42c7b-115">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="42c7b-116">Prefiere el tipo de excepción más derivado, si procede.</span><span class="sxs-lookup"><span data-stu-id="42c7b-116">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="42c7b-117">✔️ establecer la propiedad `ParamName` al iniciar una de las subclases de `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="42c7b-117">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="42c7b-118">Esta propiedad representa el nombre del parámetro que provocó que se produjera la excepción.</span><span class="sxs-lookup"><span data-stu-id="42c7b-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="42c7b-119">Tenga en cuenta que la propiedad se puede establecer mediante una de las sobrecargas del constructor.</span><span class="sxs-lookup"><span data-stu-id="42c7b-119">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="42c7b-120">✔️ usar `value` para el nombre del parámetro de valor implícito de los establecedores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="42c7b-120">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="42c7b-121">NullReferenceException, IndexOutOfRangeException y AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="42c7b-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="42c7b-122">❌ no permiten que las API que se pueden llamar públicamente inicien <xref:System.NullReferenceException>, <xref:System.AccessViolationException>o <xref:System.IndexOutOfRangeException>de forma explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="42c7b-122">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="42c7b-123">Estas excepciones están reservadas y iniciadas por el motor de ejecución y, en la mayoría de los casos, indican un error.</span><span class="sxs-lookup"><span data-stu-id="42c7b-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="42c7b-124">Realice una comprobación de argumentos para evitar producir estas excepciones.</span><span class="sxs-lookup"><span data-stu-id="42c7b-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="42c7b-125">Producir estas excepciones expone los detalles de implementación del método que pueden cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="42c7b-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="42c7b-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="42c7b-126">StackOverflowException</span></span>
 <span data-ttu-id="42c7b-127">❌ no inician <xref:System.StackOverflowException>explícitamente.</span><span class="sxs-lookup"><span data-stu-id="42c7b-127">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="42c7b-128">La excepción solo debe iniciarse explícitamente en CLR.</span><span class="sxs-lookup"><span data-stu-id="42c7b-128">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="42c7b-129">❌ no se detectan `StackOverflowException`.</span><span class="sxs-lookup"><span data-stu-id="42c7b-129">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="42c7b-130">Es casi imposible escribir código administrado que permanezca coherente en la presencia de desbordamientos de pila arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="42c7b-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="42c7b-131">Las partes no administradas de CLR siguen siendo coherentes mediante el uso de sondeos para trasladar desbordamientos de pila a lugares bien definidos en lugar de deshacer la copia de seguridad desde desbordamientos de pila arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="42c7b-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="42c7b-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="42c7b-132">OutOfMemoryException</span></span>
 <span data-ttu-id="42c7b-133">❌ no inician <xref:System.OutOfMemoryException>explícitamente.</span><span class="sxs-lookup"><span data-stu-id="42c7b-133">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="42c7b-134">Esta excepción solo la debe iniciar la infraestructura de CLR.</span><span class="sxs-lookup"><span data-stu-id="42c7b-134">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="42c7b-135">COMException, SEHException y ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="42c7b-135">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="42c7b-136">❌ no inician explícitamente <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>y <xref:System.Runtime.InteropServices.SEHException>.</span><span class="sxs-lookup"><span data-stu-id="42c7b-136">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="42c7b-137">Estas excepciones solo se producirán en la infraestructura de CLR.</span><span class="sxs-lookup"><span data-stu-id="42c7b-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="42c7b-138">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="42c7b-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="42c7b-139">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="42c7b-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="42c7b-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42c7b-140">See also</span></span>

- [<span data-ttu-id="42c7b-141">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="42c7b-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="42c7b-142">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="42c7b-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
