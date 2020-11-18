---
title: Instrucciones de diseño de miembros
description: Obtenga información sobre las directrices de diseño de miembros en .NET. Los miembros incluyen métodos, propiedades, eventos, constructores y campos.
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: 512fc3b7fde93279995a67be2fc0b285ba235f16
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820948"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="a1699-104">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="a1699-104">Member Design Guidelines</span></span>
<span data-ttu-id="a1699-105">Los métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros.</span><span class="sxs-lookup"><span data-stu-id="a1699-105">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="a1699-106">Los miembros son en última instancia los medios por los que se expone la funcionalidad del marco de trabajo a los usuarios finales de un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a1699-106">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="a1699-107">Los miembros pueden ser virtuales o no virtuales, concretos o abstractos, estáticos o de instancia, y pueden tener distintos ámbitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a1699-107">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="a1699-108">Toda esta variedad proporciona una expresividad increíble, pero al mismo tiempo requiere atención en la parte del diseñador de Framework.</span><span class="sxs-lookup"><span data-stu-id="a1699-108">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="a1699-109">En este capítulo se ofrecen instrucciones básicas que deben seguirse al diseñar miembros de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="a1699-109">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1699-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1699-110">In This Section</span></span>  
 [<span data-ttu-id="a1699-111">Sobrecarga de miembros</span><span class="sxs-lookup"><span data-stu-id="a1699-111">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="a1699-112">Diseño de propiedades</span><span class="sxs-lookup"><span data-stu-id="a1699-112">Property Design</span></span>](property.md)  
 [<span data-ttu-id="a1699-113">Diseño del constructor</span><span class="sxs-lookup"><span data-stu-id="a1699-113">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="a1699-114">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="a1699-114">Event Design</span></span>](event.md)  
 [<span data-ttu-id="a1699-115">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="a1699-115">Field Design</span></span>](field.md)  
 [<span data-ttu-id="a1699-116">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="a1699-116">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="a1699-117">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="a1699-117">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="a1699-118">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="a1699-118">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="a1699-119">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="a1699-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a1699-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="a1699-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1699-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1699-121">See also</span></span>

- [<span data-ttu-id="a1699-122">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="a1699-122">Framework Design Guidelines</span></span>](index.md)
