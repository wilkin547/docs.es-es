---
title: Generación de excepciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741669"
---
# <a name="exception-throwing"></a><span data-ttu-id="9bab8-102">Generación de excepciones</span><span class="sxs-lookup"><span data-stu-id="9bab8-102">Exception Throwing</span></span>
<span data-ttu-id="9bab8-103">Las instrucciones de generación de excepciones descritas en esta sección requieren una buena definición del significado del error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bab8-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="9bab8-104">El error de ejecución se produce siempre que un miembro no puede hacer lo que se diseñó (lo que implica el nombre de miembro).</span><span class="sxs-lookup"><span data-stu-id="9bab8-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="9bab8-105">Por ejemplo, si el método `OpenFile` no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bab8-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>

 <span data-ttu-id="9bab8-106">La mayoría de los desarrolladores se han familiarizado con el uso de excepciones para errores de uso como la división por cero o referencias nulas.</span><span class="sxs-lookup"><span data-stu-id="9bab8-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="9bab8-107">En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bab8-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>

 <span data-ttu-id="9bab8-108">❌ no devuelven códigos de error.</span><span class="sxs-lookup"><span data-stu-id="9bab8-108">❌ DO NOT return error codes.</span></span>

 <span data-ttu-id="9bab8-109">Las excepciones son el medio principal para informar de errores en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9bab8-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>

 <span data-ttu-id="9bab8-110">✔️ los errores de ejecución de informes iniciando excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-110">✔️ DO report execution failures by throwing exceptions.</span></span>

 <span data-ttu-id="9bab8-111">✔️ considere la posibilidad de terminar el proceso llamando a `System.Environment.FailFast` (.NET Framework característica 2,0) en lugar de producir una excepción si el código encuentra una situación en la que no es seguro para la ejecución posterior.</span><span class="sxs-lookup"><span data-stu-id="9bab8-111">✔️ CONSIDER terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>

 <span data-ttu-id="9bab8-112">❌ no utilice excepciones para el flujo de control normal, si es posible.</span><span class="sxs-lookup"><span data-stu-id="9bab8-112">❌ DO NOT use exceptions for the normal flow of control, if possible.</span></span>

 <span data-ttu-id="9bab8-113">A excepción de los errores del sistema y las operaciones con posibles condiciones de carrera, los diseñadores de Marcos deben diseñar las API para que los usuarios puedan escribir código que no produzca excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="9bab8-114">Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro para que los usuarios puedan escribir código que no produzca excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>

 <span data-ttu-id="9bab8-115">El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como evaluador y el miembro que realmente realiza el trabajo se denomina doer.</span><span class="sxs-lookup"><span data-stu-id="9bab8-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>

 <span data-ttu-id="9bab8-116">Hay casos en los que el patrón Tester-doer puede tener una sobrecarga de rendimiento inaceptable.</span><span class="sxs-lookup"><span data-stu-id="9bab8-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="9bab8-117">En tales casos, se debe tener en cuenta el patrón try-Parse, que se conoce como " [excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información".</span><span class="sxs-lookup"><span data-stu-id="9bab8-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>

 <span data-ttu-id="9bab8-118">✔️ Tenga en cuenta las implicaciones de rendimiento de producir excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-118">✔️ CONSIDER the performance implications of throwing exceptions.</span></span> <span data-ttu-id="9bab8-119">Las tarifas de inicio por encima de 100 por segundo suelen afectar negativamente al rendimiento de la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>

 <span data-ttu-id="9bab8-120">✔️ documentar todas las excepciones producidas por los miembros a los que se puede llamar públicamente debido a una infracción del contrato de miembros (en lugar de un error del sistema) y tratarlas como parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="9bab8-120">✔️ DO document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>

 <span data-ttu-id="9bab8-121">Las excepciones que forman parte del contrato no deben cambiar de una versión a la siguiente (es decir, el tipo de excepción no debe cambiar y no se deben agregar nuevas excepciones).</span><span class="sxs-lookup"><span data-stu-id="9bab8-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>

 <span data-ttu-id="9bab8-122">❌ no tienen miembros públicos que puedan iniciarse o no en función de alguna opción.</span><span class="sxs-lookup"><span data-stu-id="9bab8-122">❌ DO NOT have public members that can either throw or not based on some option.</span></span>

 <span data-ttu-id="9bab8-123">❌ no tienen miembros públicos que devuelven excepciones como el valor devuelto o un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="9bab8-123">❌ DO NOT have public members that return exceptions as the return value or an `out` parameter.</span></span>

 <span data-ttu-id="9bab8-124">Si se devuelven excepciones desde API públicas en lugar de generarlas, se desaprovechan muchas de las ventajas de los informes de errores basados en excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>

 <span data-ttu-id="9bab8-125">✔️ CONSIDERE el uso de métodos del generador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-125">✔️ CONSIDER using exception builder methods.</span></span>

 <span data-ttu-id="9bab8-126">Es habitual producir la misma excepción desde distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="9bab8-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="9bab8-127">Para evitar la saturación del código, use métodos auxiliares que creen excepciones e inicialicen sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9bab8-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>

 <span data-ttu-id="9bab8-128">Además, los miembros que inician excepciones no se insertan en línea.</span><span class="sxs-lookup"><span data-stu-id="9bab8-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="9bab8-129">Mover la instrucción throw dentro del generador podría permitir que el miembro esté insertado.</span><span class="sxs-lookup"><span data-stu-id="9bab8-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>

 <span data-ttu-id="9bab8-130">❌ no inician excepciones desde bloques de filtro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9bab8-130">❌ DO NOT throw exceptions from exception filter blocks.</span></span>

 <span data-ttu-id="9bab8-131">Cuando un filtro de excepción genera una excepción, el CLR detecta la excepción y el filtro devuelve false.</span><span class="sxs-lookup"><span data-stu-id="9bab8-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="9bab8-132">Este comportamiento no se distingue del filtro que se ejecuta y devuelve false explícitamente y, por tanto, es muy difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="9bab8-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>

 <span data-ttu-id="9bab8-133">❌ evitar iniciar explícitamente las excepciones de los bloques Finally.</span><span class="sxs-lookup"><span data-stu-id="9bab8-133">❌ AVOID explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="9bab8-134">Las excepciones iniciadas implícitamente que resultan de llamar a métodos que inician son aceptables.</span><span class="sxs-lookup"><span data-stu-id="9bab8-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>

 <span data-ttu-id="9bab8-135">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="9bab8-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9bab8-136">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="9bab8-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9bab8-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bab8-137">See also</span></span>

- [<span data-ttu-id="9bab8-138">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bab8-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="9bab8-139">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="9bab8-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
