---
title: Usar tipos de excepciones estándar
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ea4a61be3a76c30c564cbf98ba3318fc6c3e7d4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216101"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="fab38-102">Usar tipos de excepciones estándar</span><span class="sxs-lookup"><span data-stu-id="fab38-102">Using Standard Exception Types</span></span>
<span data-ttu-id="fab38-103">Esta sección describen las excepciones estándar proporcionadas por el marco de trabajo y los detalles de su uso.</span><span class="sxs-lookup"><span data-stu-id="fab38-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="fab38-104">La lista no es exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="fab38-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="fab38-105">Consulte la documentación de referencia de .NET Framework para el uso de otros tipos de excepción de Framework.</span><span class="sxs-lookup"><span data-stu-id="fab38-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="fab38-106">Excepción y SystemException</span><span class="sxs-lookup"><span data-stu-id="fab38-106">Exception and SystemException</span></span>  
 <span data-ttu-id="fab38-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> o <xref:System.SystemException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fab38-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="fab38-108">**X DO NOT** catch `System.Exception` o `System.SystemException` en el código de framework, a menos que vaya a producir.</span><span class="sxs-lookup"><span data-stu-id="fab38-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="fab38-109">**X AVOID** detectar `System.Exception` o `System.SystemException`, excepto en los controladores de excepciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="fab38-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="fab38-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="fab38-110">ApplicationException</span></span>  
 <span data-ttu-id="fab38-111">**X DO NOT** throw o derivar de <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="fab38-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="fab38-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="fab38-112">InvalidOperationException</span></span>  
 <span data-ttu-id="fab38-113">**✓ DO** producir una <xref:System.InvalidOperationException> si el objeto está en un estado inadecuado.</span><span class="sxs-lookup"><span data-stu-id="fab38-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="fab38-114">ArgumentException, ArgumentNullException y ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="fab38-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="fab38-115">**✓ DO** throw <xref:System.ArgumentException> o uno de sus subtipos si se pasan argumentos incorrectos a un miembro.</span><span class="sxs-lookup"><span data-stu-id="fab38-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="fab38-116">Prefiere el tipo más derivado excepción, si procede.</span><span class="sxs-lookup"><span data-stu-id="fab38-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="fab38-117">**✓ DO** establecer el `ParamName` propiedad al producir una de las subclases de `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="fab38-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="fab38-118">Esta propiedad representa el nombre del parámetro que provocó la excepción que se produzca.</span><span class="sxs-lookup"><span data-stu-id="fab38-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="fab38-119">Tenga en cuenta que la propiedad puede establecerse mediante una de las sobrecargas del constructor.</span><span class="sxs-lookup"><span data-stu-id="fab38-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="fab38-120">**✓ DO** usar `value` para el nombre del parámetro de valor implícito de establecedores de propiedades.</span><span class="sxs-lookup"><span data-stu-id="fab38-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="fab38-121">Excepción NullReferenceException, IndexOutOfRangeException y AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="fab38-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="fab38-122">**X DO NOT** permitir que las API invocables públicamente explícita o implícitamente produzca <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, o <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="fab38-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="fab38-123">Estas excepciones son reservadas y producida por el motor de ejecución y en que la mayoría de los casos indican un error.</span><span class="sxs-lookup"><span data-stu-id="fab38-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="fab38-124">Realizar comprobaciones para evitar estas excepciones de argumento.</span><span class="sxs-lookup"><span data-stu-id="fab38-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="fab38-125">Estas excepciones exponen los detalles de implementación del método que se pueden cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="fab38-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="fab38-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="fab38-126">StackOverflowException</span></span>  
 <span data-ttu-id="fab38-127">**X DO NOT** iniciar explícitamente <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="fab38-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="fab38-128">La excepción debe producirse explícitamente sólo por CLR.</span><span class="sxs-lookup"><span data-stu-id="fab38-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="fab38-129">**X DO NOT** catch `StackOverflowException`.</span><span class="sxs-lookup"><span data-stu-id="fab38-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="fab38-130">Es casi imposible escribir código administrado que siga siendo coherente en el caso de los desbordamientos de pila arbitrario.</span><span class="sxs-lookup"><span data-stu-id="fab38-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="fab38-131">Las partes no administradas de CLR siguen siendo coherentes mediante sondeos para mover los desbordamientos de pila en lugares bien definidos en lugar de reversión de los desbordamientos de pila arbitrario.</span><span class="sxs-lookup"><span data-stu-id="fab38-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="fab38-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="fab38-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="fab38-133">**X DO NOT** iniciar explícitamente <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="fab38-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="fab38-134">Esta excepción es que se produzca solo por la infraestructura de CLR.</span><span class="sxs-lookup"><span data-stu-id="fab38-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="fab38-135">ComException SEHException y ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="fab38-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="fab38-136">**X DO NOT** iniciar explícitamente <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, y <xref:System.Runtime.InteropServices.SEHException>.</span><span class="sxs-lookup"><span data-stu-id="fab38-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="fab38-137">Estas excepciones son que se produzca solo por la infraestructura de CLR.</span><span class="sxs-lookup"><span data-stu-id="fab38-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="fab38-138">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="fab38-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fab38-139">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="fab38-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab38-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab38-140">See also</span></span>

- [<span data-ttu-id="fab38-141">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fab38-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="fab38-142">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="fab38-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
