---
title: "Diseñar extensibilidad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f21e9239199ecd36432ed8f14adb896f1799506b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="d3be3-102">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="d3be3-102">Designing for Extensibility</span></span>
<span data-ttu-id="d3be3-103">Un aspecto importante del diseño de un marco de trabajo consiste en asegurarse que la extensibilidad del marco tengan en cuidadosa consideración.</span><span class="sxs-lookup"><span data-stu-id="d3be3-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="d3be3-104">Esto requiere que se conozca los costos y beneficios asociados con diversos mecanismos de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="d3be3-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="d3be3-105">Este capítulo le ayudará a decidir cuál de los mecanismos de extensibilidad: subclases, eventos, los miembros virtuales, las devoluciones de llamada y así sucesivamente, pueden satisfacer mejor los requisitos de su marco.</span><span class="sxs-lookup"><span data-stu-id="d3be3-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="d3be3-106">Hay muchas maneras de permitir la extensibilidad en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d3be3-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="d3be3-107">Abarcan desde menos eficaces pero menos costosa para una acción muy potente pero costoso.</span><span class="sxs-lookup"><span data-stu-id="d3be3-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="d3be3-108">Para cualquier requisito de extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="d3be3-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="d3be3-109">Tenga en cuenta que normalmente es posible agregar más extensibilidad más tarde, pero nunca puede dejarlo inmediatamente sin introducir cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="d3be3-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3be3-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3be3-110">In This Section</span></span>  
 [<span data-ttu-id="d3be3-111">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="d3be3-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="d3be3-112">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="d3be3-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="d3be3-113">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="d3be3-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="d3be3-114">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="d3be3-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="d3be3-115">Abstracciones (Tipos e interfaces abstractos)</span><span class="sxs-lookup"><span data-stu-id="d3be3-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="d3be3-116">Clases base para implementar abstracciones</span><span class="sxs-lookup"><span data-stu-id="d3be3-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="d3be3-117">Sellado</span><span class="sxs-lookup"><span data-stu-id="d3be3-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="d3be3-118">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="d3be3-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d3be3-119">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="d3be3-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3be3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3be3-120">See Also</span></span>  
 [<span data-ttu-id="d3be3-121">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d3be3-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
