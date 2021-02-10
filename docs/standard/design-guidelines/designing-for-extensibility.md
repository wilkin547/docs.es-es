---
description: 'Más información acerca de: Diseñar extensibilidad'
title: Diseñar extensibilidad
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 148ae25380698a5a1161fb9fbdd3cc60102e865d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642271"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="17722-103">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="17722-103">Designing for Extensibility</span></span>

<span data-ttu-id="17722-104">Un aspecto importante del diseño de un marco es asegurarse de que se ha considerado detenidamente la extensibilidad del marco.</span><span class="sxs-lookup"><span data-stu-id="17722-104">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="17722-105">Esto requiere que conozca los costos y las ventajas asociados a los diversos mecanismos de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="17722-105">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="17722-106">En este capítulo se le ayuda a decidir cuál de los mecanismos de extensibilidad (creación de subclases, eventos, miembros virtuales, devoluciones de llamada, etc.) puede cumplir mejor los requisitos de su marco.</span><span class="sxs-lookup"><span data-stu-id="17722-106">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="17722-107">Hay muchas maneras de permitir la extensibilidad en marcos.</span><span class="sxs-lookup"><span data-stu-id="17722-107">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="17722-108">Oscilan entre menos eficaces, pero menos costosas, y muy eficaces, pero costosas.</span><span class="sxs-lookup"><span data-stu-id="17722-108">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="17722-109">Para cualquier requisito de extensibilidad especificado, debe elegir el mecanismo de extensibilidad menos costoso que cumpla los requisitos.</span><span class="sxs-lookup"><span data-stu-id="17722-109">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="17722-110">Tenga en cuenta que normalmente es posible agregar más extensibilidad más adelante, pero nunca puede quitarla sin realizar cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="17722-110">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17722-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="17722-111">In This Section</span></span>  

 [<span data-ttu-id="17722-112">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="17722-112">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="17722-113">Miembros protegidos</span><span class="sxs-lookup"><span data-stu-id="17722-113">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="17722-114">Eventos y devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="17722-114">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="17722-115">Miembros virtuales</span><span class="sxs-lookup"><span data-stu-id="17722-115">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="17722-116">Abstracciones (Tipos e interfaces abstractos)</span><span class="sxs-lookup"><span data-stu-id="17722-116">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="17722-117">Clases base para implementar abstracciones</span><span class="sxs-lookup"><span data-stu-id="17722-117">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="17722-118">Sellar</span><span class="sxs-lookup"><span data-stu-id="17722-118">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="17722-119">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="17722-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="17722-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="17722-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17722-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="17722-121">See also</span></span>

- [<span data-ttu-id="17722-122">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="17722-122">Framework Design Guidelines</span></span>](index.md)
