---
description: 'Más información acerca de: Eventos y devoluciones de llamada'
title: Eventos y devoluciones de llamada
ms.date: 10/22/2008
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 8a9049808ec0f7a490889ab1f17c4d8b8e8bd2b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642154"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="a5d16-103">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="a5d16-103">Events and Callbacks</span></span>

<span data-ttu-id="a5d16-104">Las devoluciones de llamada son puntos de extensibilidad que permiten a un marco volver a llamar al código de usuario a través de un delegado.</span><span class="sxs-lookup"><span data-stu-id="a5d16-104">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="a5d16-105">Estos delegados se pasan normalmente al marco a través de un parámetro de un método.</span><span class="sxs-lookup"><span data-stu-id="a5d16-105">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="a5d16-106">Los eventos son un caso especial de devoluciones de llamada que admiten una sintaxis adecuada y coherente para proporcionar el delegado (un controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="a5d16-106">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="a5d16-107">Además, los diseñadores y la finalización de instrucciones de Visual Studio proporcionan ayuda para utilizar las API basadas en eventos.</span><span class="sxs-lookup"><span data-stu-id="a5d16-107">In addition, Visual Studio's statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="a5d16-108">(Consulte [Diseño de eventos](event.md)).</span><span class="sxs-lookup"><span data-stu-id="a5d16-108">(See [Event Design](event.md).)</span></span>

 <span data-ttu-id="a5d16-109">✔️ PLANTÉESE la posibilidad de usar devoluciones de llamada para permitir que los usuarios proporcionen código personalizado para que lo ejecute el marco.</span><span class="sxs-lookup"><span data-stu-id="a5d16-109">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="a5d16-110">✔️ PLANTÉESE la posibilidad de usar eventos para que los usuarios puedan personalizar el comportamiento de un marco sin necesidad de entender el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="a5d16-110">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="a5d16-111">✔️ OPTE por eventos en lugar de devoluciones de llamada sin formato, porque son más familiares para una gama más amplia de desarrolladores y están integrados con la finalización de declaraciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5d16-111">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="a5d16-112">❌ EVITE usar devoluciones de llamada en las API sensibles al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a5d16-112">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="a5d16-113">✔️ DEBE usar los nuevos tipos de `Func<...>`, `Action<...>` o `Expression<...>` en lugar de los delegados personalizados al definir las API con devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="a5d16-113">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="a5d16-114">`Func<...>` y `Action<...>` representan delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="a5d16-114">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="a5d16-115">`Expression<...>` representa definiciones de función que se pueden compilar e invocar posteriormente en tiempo de ejecución, pero también se pueden serializar y pasar a procesos remotos.</span><span class="sxs-lookup"><span data-stu-id="a5d16-115">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="a5d16-116">✔️ DEBE medir y comprender las implicaciones de rendimiento que supone usar `Expression<...>`, en lugar de usar los delegados `Func<...>` y `Action<...>`.</span><span class="sxs-lookup"><span data-stu-id="a5d16-116">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="a5d16-117">En la mayoría de los casos, los tipos `Expression<...>` son lógicamente equivalentes a los delegados `Func<...>` y `Action<...>`.</span><span class="sxs-lookup"><span data-stu-id="a5d16-117">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="a5d16-118">La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de procesos locales; las expresiones están indicadas para los casos en los que resulta ventajoso y posible evaluar la expresión en un proceso o equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="a5d16-118">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it's beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="a5d16-119">✔️ DEBE comprender que, al llamar a un delegado, está ejecutando código arbitrario y que podría tener repercusiones en la seguridad, la exactitud y la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a5d16-119">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="a5d16-120">*Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="a5d16-120">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a5d16-121">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="a5d16-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a5d16-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5d16-122">See also</span></span>

- [<span data-ttu-id="a5d16-123">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="a5d16-123">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="a5d16-124">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a5d16-124">Framework Design Guidelines</span></span>](index.md)
