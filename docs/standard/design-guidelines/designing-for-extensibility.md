---
title: Diseñar extensibilidad
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615604"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="49a24-102">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="49a24-102">Designing for Extensibility</span></span>
<span data-ttu-id="49a24-103">Un aspecto importante del diseño de un marco de trabajo es asegurarse de que la extensibilidad del marco se ha considerado atentamente.</span><span class="sxs-lookup"><span data-stu-id="49a24-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="49a24-104">Esto requiere que comprenda los costos y beneficios asociados con distintos mecanismos de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="49a24-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="49a24-105">Este capítulo le ayuda a decidir cuál de los mecanismos de extensibilidad: subclases, eventos, los miembros virtuales, las devoluciones de llamada y así sucesivamente, puede cumplir mejor los requisitos de su marco.</span><span class="sxs-lookup"><span data-stu-id="49a24-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="49a24-106">Hay muchas maneras para permitir la extensibilidad en marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49a24-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="49a24-107">Abarcan desde el menos eficaz pero menos costosos a muy eficaz pero costoso.</span><span class="sxs-lookup"><span data-stu-id="49a24-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="49a24-108">Para cualquier requisito extensibilidad determinado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="49a24-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="49a24-109">Tenga en cuenta que es normalmente posible agregar más extensibilidad más adelante, pero nunca puede llevarlo lejos sin introducir cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="49a24-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49a24-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="49a24-110">In This Section</span></span>  
 [<span data-ttu-id="49a24-111">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="49a24-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="49a24-112">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="49a24-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="49a24-113">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="49a24-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="49a24-114">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="49a24-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="49a24-115">Abstracciones (Tipos e interfaces abstractos)</span><span class="sxs-lookup"><span data-stu-id="49a24-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="49a24-116">Clases base para implementar abstracciones</span><span class="sxs-lookup"><span data-stu-id="49a24-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="49a24-117">Sellado</span><span class="sxs-lookup"><span data-stu-id="49a24-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="49a24-118">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="49a24-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="49a24-119">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="49a24-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a24-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="49a24-120">See also</span></span>

- [<span data-ttu-id="49a24-121">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49a24-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
