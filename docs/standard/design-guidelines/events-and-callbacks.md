---
title: Eventos y devoluciones de llamada
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 217e9eae3540e0a20afd0888d24803285d6352b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="events-and-callbacks"></a><span data-ttu-id="bb878-102">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="bb878-102">Events and Callbacks</span></span>
<span data-ttu-id="bb878-103">Las devoluciones de llamada son los puntos de extensibilidad que permiten a un marco de trabajo para volver a llamar al código de usuario a través de un delegado.</span><span class="sxs-lookup"><span data-stu-id="bb878-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="bb878-104">Estos delegados se pasan normalmente en el marco de trabajo a través de un parámetro de un método.</span><span class="sxs-lookup"><span data-stu-id="bb878-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="bb878-105">Los eventos son un caso especial de devoluciones de llamada que admite la sintaxis adecuada y coherente para suministrar al delegado (un controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="bb878-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="bb878-106">Además, la finalización de instrucciones y los diseñadores de Visual Studio proporcionan ayuda sobre el uso de API basadas en eventos.</span><span class="sxs-lookup"><span data-stu-id="bb878-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="bb878-107">(Consulte [evento diseño](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="bb878-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="bb878-108">**Considere la posibilidad de ✓** usando las devoluciones de llamada que permite a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb878-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="bb878-109">**✓ Considere la posibilidad de** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="bb878-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="bb878-110">**✓ HACER** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de los desarrolladores y se integran con la finalización de instrucciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bb878-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="bb878-111">**X evitar** usar devoluciones de llamada de API sensibles al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bb878-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="bb878-112">**✓ HACER** use la nueva `Func<...>`, `Action<...>`, o `Expression<...>` tipos en lugar de delegados personalizados, al definir las API con las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="bb878-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="bb878-113">`Func<...>`y `Action<...>` representan los delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="bb878-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="bb878-114">`Expression<...>`representa las definiciones de función que se pueden compilar y posteriormente se invoca en tiempo de ejecución pero también puedan serializar y pasar a un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="bb878-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="bb878-115">**✓ HACER** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de usar `Func<...>` y `Action<...>` delegados.</span><span class="sxs-lookup"><span data-stu-id="bb878-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="bb878-116">`Expression<...>`tipos están en la mayoría de los casos lógicamente equivalente a `Func<...>` y `Action<...>` delegados.</span><span class="sxs-lookup"><span data-stu-id="bb878-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="bb878-117">La diferencia principal entre ellas es que los delegados están diseñados para usarse en escenarios de proceso local; expresiones están diseñadas para los casos donde resulta beneficioso y posibles evaluar la expresión en una máquina o un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="bb878-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="bb878-118">**✓ HACER** entender que mediante una llamada a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, la exactitud y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="bb878-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="bb878-119">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="bb878-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bb878-120">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bb878-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb878-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb878-121">See Also</span></span>  
 [<span data-ttu-id="bb878-122">Diseñar para la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="bb878-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="bb878-123">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb878-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
