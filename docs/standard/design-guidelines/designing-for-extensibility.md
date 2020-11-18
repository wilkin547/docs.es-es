---
title: Diseñar extensibilidad
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 9e75ef433f3bd9af34e8dd40331a8267755e59fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821390"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="3e0bd-102">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="3e0bd-102">Designing for Extensibility</span></span>
<span data-ttu-id="3e0bd-103">Un aspecto importante del diseño de un marco es asegurarse de que se ha tenido cuidado en la extensibilidad del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="3e0bd-104">Esto requiere que comprenda los costos y beneficios asociados con los distintos mecanismos de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="3e0bd-105">Este capítulo le ayuda a decidir cuál de los mecanismos de extensibilidad (subclases, eventos, miembros virtuales, devoluciones de llamada, etc.) puede satisfacer mejor los requisitos de su marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="3e0bd-106">Hay muchas maneras de permitir la extensibilidad en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="3e0bd-107">Van desde menos eficaz, pero menos costosas hasta muy eficaces pero costosas.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="3e0bd-108">Para cualquier requisito de extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="3e0bd-109">Tenga en cuenta que normalmente es posible agregar más extensibilidad más adelante, pero nunca puede quitarla sin introducir cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="3e0bd-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e0bd-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3e0bd-110">In This Section</span></span>  
 [<span data-ttu-id="3e0bd-111">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="3e0bd-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="3e0bd-112">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="3e0bd-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="3e0bd-113">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="3e0bd-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="3e0bd-114">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="3e0bd-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="3e0bd-115">Abstracciones (tipos e interfaces abstractos)</span><span class="sxs-lookup"><span data-stu-id="3e0bd-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="3e0bd-116">Clases base para implementar abstracciones</span><span class="sxs-lookup"><span data-stu-id="3e0bd-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="3e0bd-117">Sellar</span><span class="sxs-lookup"><span data-stu-id="3e0bd-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="3e0bd-118">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="3e0bd-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3e0bd-119">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="3e0bd-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e0bd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e0bd-120">See also</span></span>

- [<span data-ttu-id="3e0bd-121">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="3e0bd-121">Framework Design Guidelines</span></span>](index.md)
