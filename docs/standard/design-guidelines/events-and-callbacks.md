---
title: Eventos y devoluciones de llamada
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 7dab759ba48104530fc41e46f6f2bba18d6c4456
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741655"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="178b7-102">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="178b7-102">Events and Callbacks</span></span>
<span data-ttu-id="178b7-103">Las devoluciones de llamada son puntos de extensibilidad que permiten a un marco volver a llamar al código de usuario a través de un delegado.</span><span class="sxs-lookup"><span data-stu-id="178b7-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="178b7-104">Estos delegados se pasan normalmente al marco de trabajo a través de un parámetro de un método.</span><span class="sxs-lookup"><span data-stu-id="178b7-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>

 <span data-ttu-id="178b7-105">Los eventos son un caso especial de devoluciones de llamada que admite una sintaxis adecuada y coherente para proporcionar el delegado (un controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="178b7-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="178b7-106">Además, los diseñadores y la finalización de instrucciones de Visual Studio proporcionan ayuda para el uso de API basadas en eventos.</span><span class="sxs-lookup"><span data-stu-id="178b7-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="178b7-107">(Consulte [diseño de eventos](../../../docs/standard/design-guidelines/event.md)).</span><span class="sxs-lookup"><span data-stu-id="178b7-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>

 <span data-ttu-id="178b7-108">✔️ considere la posibilidad de usar devoluciones de llamada para permitir que los usuarios proporcionen código personalizado para que lo ejecute el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="178b7-108">✔️ CONSIDER using callbacks to allow users to provide custom code to be executed by the framework.</span></span>

 <span data-ttu-id="178b7-109">✔️ considere la posibilidad de usar eventos para que los usuarios puedan personalizar el comportamiento de un marco sin necesidad de entender el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="178b7-109">✔️ CONSIDER using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>

 <span data-ttu-id="178b7-110">✔️ prefieren eventos en lugar de devoluciones de llamada sin formato, ya que están más familiarizados con una amplia gama de desarrolladores y se integran con la finalización de instrucciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="178b7-110">✔️ DO prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>

 <span data-ttu-id="178b7-111">❌ evitar el uso de devoluciones de llamada en las API sensibles al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="178b7-111">❌ AVOID using callbacks in performance-sensitive APIs.</span></span>

 <span data-ttu-id="178b7-112">✔️ usar los nuevos tipos de `Func<...>`, `Action<...>`o `Expression<...>` en lugar de los delegados personalizados, al definir las API con devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="178b7-112">✔️ DO use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>

 <span data-ttu-id="178b7-113">`Func<...>` y `Action<...>` representan delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="178b7-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="178b7-114">`Expression<...>` representa definiciones de función que se pueden compilar e invocar posteriormente en tiempo de ejecución, pero también se pueden serializar y pasar a procesos remotos.</span><span class="sxs-lookup"><span data-stu-id="178b7-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>

 <span data-ttu-id="178b7-115">✔️ medir y comprender las implicaciones de rendimiento del uso de `Expression<...>`, en lugar de usar delegados `Func<...>` y `Action<...>`.</span><span class="sxs-lookup"><span data-stu-id="178b7-115">✔️ DO measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>

 <span data-ttu-id="178b7-116">`Expression<...>` tipos son en la mayoría de los casos lógicamente equivalentes a los delegados de `Func<...>` y `Action<...>`.</span><span class="sxs-lookup"><span data-stu-id="178b7-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="178b7-117">La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de procesos locales; las expresiones están destinadas a los casos en los que resulta ventajoso y posible evaluar la expresión en un proceso o equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="178b7-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>

 <span data-ttu-id="178b7-118">✔️ comprender que, al llamar a un delegado, está ejecutando código arbitrario y que podría tener repercusiones en la seguridad, la corrección y la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="178b7-118">✔️ DO understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>

 <span data-ttu-id="178b7-119">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="178b7-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="178b7-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="178b7-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="178b7-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="178b7-121">See also</span></span>

- [<span data-ttu-id="178b7-122">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="178b7-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="178b7-123">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="178b7-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
