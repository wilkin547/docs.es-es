---
title: Instrucciones de diseño de miembros
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: KrzysztofCwalina
ms.openlocfilehash: d7023bbe59eb3590af47952a2fe24c5f40b3ca68
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155267"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="5d082-102">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="5d082-102">Member Design Guidelines</span></span>
<span data-ttu-id="5d082-103">Los métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros.</span><span class="sxs-lookup"><span data-stu-id="5d082-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="5d082-104">En última instancia, los miembros son el medio por el que se expone la funcionalidad del marco a los usuarios finales de un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d082-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="5d082-105">Los miembros pueden ser virtual o no virtual, concreta o abstracto, estático o instancia y pueden tener varios ámbitos diferentes de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="5d082-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="5d082-106">Toda esta variedad proporciona expresividad increíble, pero al mismo tiempo que requiere atención por parte del Diseñador de framework.</span><span class="sxs-lookup"><span data-stu-id="5d082-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="5d082-107">Este capítulo ofrece directrices básicas que se deben seguir al diseñar a los miembros de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="5d082-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d082-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5d082-108">In This Section</span></span>  
 [<span data-ttu-id="5d082-109">Sobrecarga de miembro</span><span class="sxs-lookup"><span data-stu-id="5d082-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="5d082-110">Diseño de propiedades</span><span class="sxs-lookup"><span data-stu-id="5d082-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="5d082-111">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="5d082-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="5d082-112">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="5d082-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="5d082-113">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="5d082-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="5d082-114">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="5d082-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="5d082-115">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="5d082-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="5d082-116">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="5d082-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="5d082-117">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="5d082-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5d082-118">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5d082-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d082-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d082-119">See also</span></span>

- [<span data-ttu-id="5d082-120">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d082-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
