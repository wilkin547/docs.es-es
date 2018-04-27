---
title: Generación de excepciones
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 47c16ac94054fff193b1f5976fe7f04f10a39ecd
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="exception-throwing"></a><span data-ttu-id="4e16c-102">Generación de excepciones</span><span class="sxs-lookup"><span data-stu-id="4e16c-102">Exception Throwing</span></span>
<span data-ttu-id="4e16c-103">Generación de excepciones directrices descritas en esta sección requieren una buena definición del significado del error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4e16c-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="4e16c-104">Se produce un error de ejecución cada vez que un miembro no puede hacer lo que estaba diseñado para hacer (lo que el nombre de miembro implica).</span><span class="sxs-lookup"><span data-stu-id="4e16c-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="4e16c-105">Por ejemplo, si la `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4e16c-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="4e16c-106">Mayoría de los desarrolladores han familiarizado con excepciones para los errores de uso como la división por cero o referencias nulas.</span><span class="sxs-lookup"><span data-stu-id="4e16c-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="4e16c-107">En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4e16c-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="4e16c-108">**X DO NOT** devolver códigos de error.</span><span class="sxs-lookup"><span data-stu-id="4e16c-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="4e16c-109">Las excepciones son el medio principal de informar de errores en los marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4e16c-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="4e16c-110">**✓ HACER** notificar errores de ejecución iniciando excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="4e16c-111">**✓ Considere la posibilidad de** la terminación del proceso mediante una llamada a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de producir una excepción si el código encuentra una situación donde no es seguro para la ejecución aún más.</span><span class="sxs-lookup"><span data-stu-id="4e16c-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="4e16c-112">**X DO NOT** usar excepciones para el flujo normal de control, si es posible.</span><span class="sxs-lookup"><span data-stu-id="4e16c-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="4e16c-113">Salvo los errores del sistema y operaciones con posibles condiciones de carrera, diseñadores de marco de trabajo deberían diseñar las API para que los usuarios puedan escribir código que no produce excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="4e16c-114">Por ejemplo, puede proporcionar un mecanismo para comprobar las condiciones previas antes de llamar a un miembro, por lo que los usuarios puedan escribir código que no produce excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="4e16c-115">El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como una herramienta de comprobación y el miembro que hace realmente el trabajo se denomina una acción.</span><span class="sxs-lookup"><span data-stu-id="4e16c-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="4e16c-116">Hay casos en el patrón de acción de evaluador puede tener una sobrecarga de rendimiento inaceptable.</span><span class="sxs-lookup"><span data-stu-id="4e16c-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="4e16c-117">En tales casos, debe considerarse el patrón de Try-análisis denominadas (vea [excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="4e16c-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="4e16c-118">**✓ Considere la posibilidad de** las implicaciones de rendimiento de inicio de excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="4e16c-119">Las tasas de throw por encima de 100 por segundo son propensos a afectar notablemente el rendimiento de la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="4e16c-120">**✓ HACER** documento todas las excepciones iniciadas por miembros invocables públicamente debido a una infracción del miembro del contrato (en lugar de un error del sistema) y tratan como parte de su contrato.</span><span class="sxs-lookup"><span data-stu-id="4e16c-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="4e16c-121">Las excepciones que forman parte del contrato no deberían cambiar de una versión a la siguiente (es decir, no debería cambiar el tipo de excepción y no se deben agregar nuevas excepciones).</span><span class="sxs-lookup"><span data-stu-id="4e16c-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="4e16c-122">**X DO NOT** tener miembros públicos que pueden ya sea throw o no en función de alguna opción.</span><span class="sxs-lookup"><span data-stu-id="4e16c-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="4e16c-123">**X DO NOT** tiene miembros públicos que devuelven las excepciones como el valor devuelto o un `out` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4e16c-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="4e16c-124">Devolver las excepciones de las API públicas en lugar de producir ellos frustra muchas de las ventajas de informe de errores basado en excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="4e16c-125">**✓ Considere la posibilidad de** mediante métodos de generador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="4e16c-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="4e16c-126">Es común para que se produzca la misma excepción desde distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="4e16c-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="4e16c-127">Para evitar la cantidad de código, use métodos auxiliares que crean excepciones e inicializan sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="4e16c-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="4e16c-128">Además, los miembros que producen excepciones no obtienen entre líneas.</span><span class="sxs-lookup"><span data-stu-id="4e16c-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="4e16c-129">Mover la instrucción throw en el generador puede permitir que el miembro se inserte.</span><span class="sxs-lookup"><span data-stu-id="4e16c-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="4e16c-130">**X DO NOT** genere excepciones desde bloques de filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="4e16c-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="4e16c-131">Cuando un filtro de excepción produce una excepción, se detecta la excepción de CLR y el filtro devuelve false.</span><span class="sxs-lookup"><span data-stu-id="4e16c-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="4e16c-132">Este comportamiento es indistinguible desde que el filtro se ejecuta y devuelve false explícitamente y por lo tanto, es muy difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="4e16c-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="4e16c-133">**X evitar** iniciar explícitamente excepciones desde bloques finally.</span><span class="sxs-lookup"><span data-stu-id="4e16c-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="4e16c-134">Las excepciones iniciadas implícitamente resultante de la llamada a métodos que inician son aceptables.</span><span class="sxs-lookup"><span data-stu-id="4e16c-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="4e16c-135">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="4e16c-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4e16c-136">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4e16c-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e16c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e16c-137">See Also</span></span>  
 [<span data-ttu-id="4e16c-138">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4e16c-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="4e16c-139">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="4e16c-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
