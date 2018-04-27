---
title: Instrucciones de diseño de miembros
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f4e33735a934b1ac41c34ccb9698c172ada28e1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="member-design-guidelines"></a><span data-ttu-id="910a8-102">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="910a8-102">Member Design Guidelines</span></span>
<span data-ttu-id="910a8-103">Métodos, propiedades, eventos, constructores y campos se conocen colectivamente como miembros.</span><span class="sxs-lookup"><span data-stu-id="910a8-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="910a8-104">Los miembros en última instancia son el medio por el que la funcionalidad de framework se expone a los usuarios finales de un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="910a8-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="910a8-105">Los miembros pueden ser virtual o no virtual, concreta o abstracto, estático o instancia y pueden tener varios ámbitos diferentes de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="910a8-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="910a8-106">Todos los esta variedad proporciona expresividad increíble pero al mismo tiempo requiere atención por parte del Diseñador de framework.</span><span class="sxs-lookup"><span data-stu-id="910a8-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="910a8-107">Este capítulo proporciona instrucciones básicas que se deben seguir al diseñar a los miembros de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="910a8-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="910a8-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="910a8-108">In This Section</span></span>  
 [<span data-ttu-id="910a8-109">Sobrecarga de miembro</span><span class="sxs-lookup"><span data-stu-id="910a8-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="910a8-110">Diseño de propiedades</span><span class="sxs-lookup"><span data-stu-id="910a8-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="910a8-111">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="910a8-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="910a8-112">Diseño de eventos</span><span class="sxs-lookup"><span data-stu-id="910a8-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="910a8-113">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="910a8-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="910a8-114">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="910a8-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="910a8-115">Sobrecargas de operador</span><span class="sxs-lookup"><span data-stu-id="910a8-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="910a8-116">Diseño de parámetros</span><span class="sxs-lookup"><span data-stu-id="910a8-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="910a8-117">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="910a8-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="910a8-118">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="910a8-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="910a8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="910a8-119">See Also</span></span>  
 [<span data-ttu-id="910a8-120">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="910a8-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
