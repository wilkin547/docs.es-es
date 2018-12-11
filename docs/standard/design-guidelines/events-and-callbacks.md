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
author: KrzysztofCwalina
ms.openlocfilehash: c9ed52c5a313676baeba66f5cb79c7a56927babb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154429"
---
# <a name="events-and-callbacks"></a><span data-ttu-id="6a44e-102">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="6a44e-102">Events and Callbacks</span></span>
<span data-ttu-id="6a44e-103">Las devoluciones de llamada son puntos de extensibilidad que permiten un marco de trabajo para volver a llamar al código de usuario a través de un delegado.</span><span class="sxs-lookup"><span data-stu-id="6a44e-103">Callbacks are extensibility points that allow a framework to call back into user code through a delegate.</span></span> <span data-ttu-id="6a44e-104">Estos delegados se pasan normalmente en el marco de trabajo a través de un parámetro de un método.</span><span class="sxs-lookup"><span data-stu-id="6a44e-104">These delegates are usually passed to the framework through a parameter of a method.</span></span>  
  
 <span data-ttu-id="6a44e-105">Los eventos son un caso especial de devoluciones de llamada que admite la sintaxis adecuada y coherente para suministrar al delegado (un controlador de eventos).</span><span class="sxs-lookup"><span data-stu-id="6a44e-105">Events are a special case of callbacks that supports convenient and consistent syntax for supplying the delegate (an event handler).</span></span> <span data-ttu-id="6a44e-106">Además, la finalización de instrucciones y los diseñadores de Visual Studio proporcionan ayuda sobre cómo usar las API basadas en eventos.</span><span class="sxs-lookup"><span data-stu-id="6a44e-106">In addition, Visual Studio’s statement completion and designers provide help in using event-based APIs.</span></span> <span data-ttu-id="6a44e-107">(Consulte [diseño eventos](../../../docs/standard/design-guidelines/event.md).)</span><span class="sxs-lookup"><span data-stu-id="6a44e-107">(See [Event Design](../../../docs/standard/design-guidelines/event.md).)</span></span>  
  
 <span data-ttu-id="6a44e-108">**✓ CONSIDER** usando las devoluciones de llamada que permite a los usuarios proporcionar código personalizado para ser ejecutado por el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6a44e-108">**✓ CONSIDER** using callbacks to allow users to provide custom code to be executed by the framework.</span></span>  
  
 <span data-ttu-id="6a44e-109">**✓ CONSIDER** mediante eventos para permitir a los usuarios personalizar el comportamiento de un marco de trabajo sin necesidad de entender el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="6a44e-109">**✓ CONSIDER** using events to allow users to customize the behavior of a framework without the need for understanding object-oriented design.</span></span>  
  
 <span data-ttu-id="6a44e-110">**✓ DO** eventos son preferibles las devoluciones de llamada sin formato, porque son mucho más familiares para una gama más amplia de los desarrolladores y se integran con la finalización de instrucciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6a44e-110">**✓ DO** prefer events over plain callbacks, because they are more familiar to a broader range of developers and are integrated with Visual Studio statement completion.</span></span>  
  
 <span data-ttu-id="6a44e-111">**X AVOID** usar devoluciones de llamada de API sensibles al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6a44e-111">**X AVOID** using callbacks in performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="6a44e-112">**✓ DO** use la nueva `Func<...>`, `Action<...>`, o `Expression<...>` tipos en lugar de delegados personalizados, al definir las API con las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="6a44e-112">**✓ DO** use the new `Func<...>`, `Action<...>`, or `Expression<...>` types instead of custom delegates, when defining APIs with callbacks.</span></span>  
  
 <span data-ttu-id="6a44e-113">`Func<...>` y `Action<...>` representan los delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="6a44e-113">`Func<...>` and `Action<...>` represent generic delegates.</span></span> <span data-ttu-id="6a44e-114">`Expression<...>` representa las definiciones de función que se pueden compilar y posteriormente se invoca en tiempo de ejecución, pero puede también serializarse y pasarse a procesos remotos.</span><span class="sxs-lookup"><span data-stu-id="6a44e-114">`Expression<...>` represents function definitions that can be compiled and subsequently invoked at runtime but can also be serialized and passed to remote processes.</span></span>  
  
 <span data-ttu-id="6a44e-115">**✓ DO** medir y comprender las implicaciones de rendimiento de uso `Expression<...>`, en lugar de usar `Func<...>` y `Action<...>` delegados.</span><span class="sxs-lookup"><span data-stu-id="6a44e-115">**✓ DO** measure and understand performance implications of using `Expression<...>`, instead of using `Func<...>` and `Action<...>` delegates.</span></span>  
  
 <span data-ttu-id="6a44e-116">`Expression<...>` tipos están en la mayoría de los casos lógicamente equivalente a `Func<...>` y `Action<...>` delegados.</span><span class="sxs-lookup"><span data-stu-id="6a44e-116">`Expression<...>` types are in most cases logically equivalent to `Func<...>` and `Action<...>` delegates.</span></span> <span data-ttu-id="6a44e-117">La diferencia principal entre ellos es que los delegados están diseñados para usarse en escenarios de proceso local; las expresiones están pensadas para casos donde resulta beneficioso y posibles evaluar la expresión en una máquina o un proceso remoto.</span><span class="sxs-lookup"><span data-stu-id="6a44e-117">The main difference between them is that the delegates are intended to be used in local process scenarios; expressions are intended for cases where it’s beneficial and possible to evaluate the expression in a remote process or machine.</span></span>  
  
 <span data-ttu-id="6a44e-118">**✓ DO** entender que mediante una llamada a un delegado, se ejecuta código arbitrario y que podría tener repercusiones de seguridad, la exactitud y compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="6a44e-118">**✓ DO** understand that by calling a delegate, you are executing arbitrary code and that could have security, correctness, and compatibility repercussions.</span></span>  
  
 <span data-ttu-id="6a44e-119">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6a44e-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6a44e-120">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6a44e-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a44e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a44e-121">See also</span></span>

- [<span data-ttu-id="6a44e-122">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="6a44e-122">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="6a44e-123">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a44e-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
