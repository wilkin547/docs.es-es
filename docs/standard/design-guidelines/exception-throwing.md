---
description: 'Más información acerca de: Generación de excepciones'
title: Generación de excepciones
ms.date: 10/22/2008
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: b1cf7a4eecc32a9f76ea06c47dd6c16d3afe5470
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642141"
---
# <a name="exception-throwing"></a><span data-ttu-id="fb15c-103">Generación de excepciones</span><span class="sxs-lookup"><span data-stu-id="fb15c-103">Exception Throwing</span></span>

<span data-ttu-id="fb15c-104">Las instrucciones de generación de excepciones descritas en esta sección precisan que definamos bien el significado de "error de ejecución".</span><span class="sxs-lookup"><span data-stu-id="fb15c-104">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="fb15c-105">El error de ejecución se produce siempre que un miembro no puede hacer lo que se le diseñó (indicado en el propio nombre del miembro).</span><span class="sxs-lookup"><span data-stu-id="fb15c-105">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="fb15c-106">Por ejemplo, si el método `OpenFile` no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb15c-106">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>

 <span data-ttu-id="fb15c-107">La mayoría de los desarrolladores se han familiarizado con el uso de las excepciones de errores de uso, como la división por cero o las referencias nulas.</span><span class="sxs-lookup"><span data-stu-id="fb15c-107">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="fb15c-108">En el marco, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb15c-108">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>

 <span data-ttu-id="fb15c-109">❌ NO devuelva códigos de error.</span><span class="sxs-lookup"><span data-stu-id="fb15c-109">❌ DO NOT return error codes.</span></span>

 <span data-ttu-id="fb15c-110">Las excepciones son el medio principal para informar de errores en marcos.</span><span class="sxs-lookup"><span data-stu-id="fb15c-110">Exceptions are the primary means of reporting errors in frameworks.</span></span>

 <span data-ttu-id="fb15c-111">✔️ Informe de los errores de ejecución generando excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-111">✔️ DO report execution failures by throwing exceptions.</span></span>

 <span data-ttu-id="fb15c-112">✔️ Recomendamos terminar el proceso llamando a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de generar una excepción si el código encuentra una situación en la que no es seguro ejecutarse posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb15c-112">✔️ CONSIDER terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>

 <span data-ttu-id="fb15c-113">❌ NO utilice excepciones para el flujo de control normal, si es posible.</span><span class="sxs-lookup"><span data-stu-id="fb15c-113">❌ DO NOT use exceptions for the normal flow of control, if possible.</span></span>

 <span data-ttu-id="fb15c-114">A excepción de los errores del sistema y las operaciones con posibles condiciones de carrera, los diseñadores de marcos deben diseñar las API para que los usuarios puedan escribir código que no genere excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-114">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="fb15c-115">Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro para que los usuarios puedan escribir código que no genere excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-115">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>

 <span data-ttu-id="fb15c-116">El miembro que se usa para comprobar las condiciones previas de otro miembro suele denominarse "evaluador" y el miembro que realmente realiza el trabajo se llama "doer".</span><span class="sxs-lookup"><span data-stu-id="fb15c-116">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>

 <span data-ttu-id="fb15c-117">Hay casos en los que el patrón tester-doer puede tener una sobrecarga de rendimiento inaceptable.</span><span class="sxs-lookup"><span data-stu-id="fb15c-117">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="fb15c-118">En estos casos, se debe tener en cuenta el patrón llamado "try-parse" (consulte [Excepciones y rendimiento](exceptions-and-performance.md) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="fb15c-118">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](exceptions-and-performance.md) for more information).</span></span>

 <span data-ttu-id="fb15c-119">✔️ Tenga en cuenta las implicaciones de rendimiento que tiene generar excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-119">✔️ CONSIDER the performance implications of throwing exceptions.</span></span> <span data-ttu-id="fb15c-120">Las tasas de generación de excepciones que estén por encima de 100 por segundo suelen afectar negativamente al rendimiento de la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-120">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>

 <span data-ttu-id="fb15c-121">✔️ Documente todas las excepciones generadas por los miembros invocables públicamente debido a una infracción del contrato de miembros (en lugar de un error del sistema) y considérelas como parte del contrato.</span><span class="sxs-lookup"><span data-stu-id="fb15c-121">✔️ DO document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>

 <span data-ttu-id="fb15c-122">Las excepciones que forman parte del contrato no deberían cambiar de una versión a la siguiente (es decir, el tipo de excepción no debe cambiar y no se deben agregar nuevas excepciones).</span><span class="sxs-lookup"><span data-stu-id="fb15c-122">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>

 <span data-ttu-id="fb15c-123">❌ NO tenga miembros públicos que puedan iniciarse o no en función de alguna opción.</span><span class="sxs-lookup"><span data-stu-id="fb15c-123">❌ DO NOT have public members that can either throw or not based on some option.</span></span>

 <span data-ttu-id="fb15c-124">❌ NO tenga miembros públicos que devuelvan excepciones como el valor devuelto o un parámetro `out`.</span><span class="sxs-lookup"><span data-stu-id="fb15c-124">❌ DO NOT have public members that return exceptions as the return value or an `out` parameter.</span></span>

 <span data-ttu-id="fb15c-125">Si se devuelven excepciones desde API públicas en lugar de generarlas, se desaprovechan muchas de las ventajas de los informes de errores basados en excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-125">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>

 <span data-ttu-id="fb15c-126">✔️ Recomendamos usar métodos del generador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-126">✔️ CONSIDER using exception builder methods.</span></span>

 <span data-ttu-id="fb15c-127">Es habitual generar la misma excepción desde distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="fb15c-127">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="fb15c-128">Para evitar el sobredimensionamiento del código, use métodos auxiliares que creen excepciones e inicialicen sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="fb15c-128">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>

 <span data-ttu-id="fb15c-129">Además, los miembros que generan excepciones no se insertan en línea.</span><span class="sxs-lookup"><span data-stu-id="fb15c-129">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="fb15c-130">Mover la instrucción throw dentro del generador podría permitir que el miembro quede insertado.</span><span class="sxs-lookup"><span data-stu-id="fb15c-130">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>

 <span data-ttu-id="fb15c-131">❌ NO genere excepciones desde bloques de filtros de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb15c-131">❌ DO NOT throw exceptions from exception filter blocks.</span></span>

 <span data-ttu-id="fb15c-132">Cuando un filtro de excepción genera una excepción, CLR la detecta y el filtro devuelve el valor false.</span><span class="sxs-lookup"><span data-stu-id="fb15c-132">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="fb15c-133">Este comportamiento es idéntico al del filtro que se ejecuta y devuelve el valor false explícitamente y, por lo tanto, es muy difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="fb15c-133">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>

 <span data-ttu-id="fb15c-134">❌ EVITE generar explícitamente excepciones de bloques Finally.</span><span class="sxs-lookup"><span data-stu-id="fb15c-134">❌ AVOID explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="fb15c-135">Se aceptan las excepciones generadas implícitamente como consecuencia de llamar a métodos que se inician.</span><span class="sxs-lookup"><span data-stu-id="fb15c-135">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>

 <span data-ttu-id="fb15c-136">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="fb15c-136">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="fb15c-137">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="fb15c-137">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fb15c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb15c-138">See also</span></span>

- [<span data-ttu-id="fb15c-139">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fb15c-139">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="fb15c-140">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="fb15c-140">Design Guidelines for Exceptions</span></span>](exceptions.md)
