---
title: Abstracciones (Tipos e interfaces abstractos)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 276c5883487d8fba47d7fb80060d4c947e0f6cd6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="c1286-102">Abstracciones (Tipos e interfaces abstractos)</span><span class="sxs-lookup"><span data-stu-id="c1286-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="c1286-103">Una abstracción es un tipo que describe un contrato, pero no proporciona una implementación completa del contrato.</span><span class="sxs-lookup"><span data-stu-id="c1286-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="c1286-104">Abstracciones normalmente se implementan como interfaces o clases abstractas y vienen con un conjunto de documentación de referencia que describe la semántica necesaria de los tipos que implementan el contrato bien definido.</span><span class="sxs-lookup"><span data-stu-id="c1286-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="c1286-105">Algunas de las abstracciones más importantes en .NET Framework son <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, y <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c1286-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="c1286-106">Puede ampliar los marcos de trabajo mediante la implementación de un tipo concreto que admita el contrato de una abstracción y usar este tipo concreto con framework API consumo (que opera en) la abstracción.</span><span class="sxs-lookup"><span data-stu-id="c1286-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="c1286-107">Es muy difícil de diseñar una abstracción lógica y útil que es capaz de soportar la prueba de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1286-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="c1286-108">La dificultad principal es obtener el conjunto de miembros, nada más y menos no correcto.</span><span class="sxs-lookup"><span data-stu-id="c1286-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="c1286-109">Si una abstracción tiene demasiados miembros, resulta difícil o imposible implementar.</span><span class="sxs-lookup"><span data-stu-id="c1286-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="c1286-110">Si tiene demasiado pocos miembros para la funcionalidad prometido, resulta inútil en muchos escenarios interesantes.</span><span class="sxs-lookup"><span data-stu-id="c1286-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="c1286-111">Hay demasiados abstracciones en un marco de trabajo también afectar negativamente al facilidad de uso de framework.</span><span class="sxs-lookup"><span data-stu-id="c1286-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="c1286-112">A menudo resulta muy difícil de comprender una abstracción sin conocer cómo encaja en la imagen más grande de la API de la abstracción y las implementaciones concretas.</span><span class="sxs-lookup"><span data-stu-id="c1286-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="c1286-113">Además, los nombres de extracciones y sus miembros son necesariamente abstractos, que a menudo hace que sean crípticos y distante sin conocer primero el contexto más amplio de su uso.</span><span class="sxs-lookup"><span data-stu-id="c1286-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="c1286-114">Sin embargo, abstracciones proporcionan extensibilidad muy eficaz que a menudo no pueden coincidir con los otros mecanismos de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="c1286-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="c1286-115">Únicamente son el núcleo de muchos patrones de arquitectura, como complementos, inversión de control (IoC), canalizaciones y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c1286-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="c1286-116">También son muy importantes para poder realizar pruebas de marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1286-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="c1286-117">Buena abstracciones permiten pesadas dependencias con el fin de pruebas unitarias de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="c1286-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="c1286-118">En resumen, las abstracciones son responsables de la riqueza de los marcos modernas orientada a objetos solicitada.</span><span class="sxs-lookup"><span data-stu-id="c1286-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="c1286-119">**X DO NOT** proporcionan abstracciones a menos que se prueban mediante el desarrollo de varias implementaciones concretas y consumir las abstracciones de API.</span><span class="sxs-lookup"><span data-stu-id="c1286-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="c1286-120">**✓ HACER** Elija cuidadosamente entre una clase abstracta y una interfaz al diseñar una abstracción.</span><span class="sxs-lookup"><span data-stu-id="c1286-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="c1286-121">**✓ Considere la posibilidad de** proporcionar pruebas de referencia para implementaciones concretas de abstracciones.</span><span class="sxs-lookup"><span data-stu-id="c1286-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="c1286-122">Dichas pruebas deben permitir a los usuarios comprobar si sus implementaciones cumplen correctamente el contrato.</span><span class="sxs-lookup"><span data-stu-id="c1286-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="c1286-123">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="c1286-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c1286-124">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c1286-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1286-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1286-125">See Also</span></span>  
 [<span data-ttu-id="c1286-126">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c1286-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="c1286-127">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="c1286-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
