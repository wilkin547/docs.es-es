---
title: Sellar
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a9ea7fd4f5df08631231db08ba7943a9c131012
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="sealing"></a><span data-ttu-id="051c9-102">Sellar</span><span class="sxs-lookup"><span data-stu-id="051c9-102">Sealing</span></span>
<span data-ttu-id="051c9-103">Una de las características de marcos de trabajo orientado a objetos es que los desarrolladores pueden extender y personalizarlas de maneras no anticipados por los diseñadores de framework.</span><span class="sxs-lookup"><span data-stu-id="051c9-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="051c9-104">Se trata de la eficacia y el riesgo de diseño extensible.</span><span class="sxs-lookup"><span data-stu-id="051c9-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="051c9-105">Cuando se diseña el marco, es, por lo tanto, muy importante diseñar cuidadosamente para la extensibilidad cuando se desea y para limitar la extensibilidad cuando es peligroso.</span><span class="sxs-lookup"><span data-stu-id="051c9-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="051c9-106">Un mecanismo eficaz que evita la extensibilidad está sellado.</span><span class="sxs-lookup"><span data-stu-id="051c9-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="051c9-107">También puede proteger la clase o el miembros individuales.</span><span class="sxs-lookup"><span data-stu-id="051c9-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="051c9-108">Sellar una clase, impide que los usuarios heredan de la clase.</span><span class="sxs-lookup"><span data-stu-id="051c9-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="051c9-109">Sellado de un miembro, impide que los usuarios reemplazar a un miembro determinado.</span><span class="sxs-lookup"><span data-stu-id="051c9-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="051c9-110">**X DO NOT** sellar clases sin tener una buena razón para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="051c9-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="051c9-111">Sellar una clase porque no se piensa en un escenario de extensibilidad no es una buena razón.</span><span class="sxs-lookup"><span data-stu-id="051c9-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="051c9-112">Los usuarios de Framework desean heredar de clases por distintas razones nonobvious, como agregar miembros de comodidad.</span><span class="sxs-lookup"><span data-stu-id="051c9-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="051c9-113">Vea [clases no selladas](../../../docs/standard/design-guidelines/unsealed-classes.md) para obtener ejemplos de motivos nonobvious los usuarios desean heredar de un tipo.</span><span class="sxs-lookup"><span data-stu-id="051c9-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="051c9-114">Buenos motivos para sellar una clase son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="051c9-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="051c9-115">La clase es una clase estática.</span><span class="sxs-lookup"><span data-stu-id="051c9-115">The class is a static class.</span></span> <span data-ttu-id="051c9-116">Vea [diseño de clases estáticas](../../../docs/standard/design-guidelines/static-class.md).</span><span class="sxs-lookup"><span data-stu-id="051c9-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="051c9-117">La clase almacena información confidencial de seguridad en los miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="051c9-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="051c9-118">La clase hereda a muchos miembros virtuales y el costo del sellado de forma individual superaría con creces las ventajas de dejar la clase no sellada.</span><span class="sxs-lookup"><span data-stu-id="051c9-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="051c9-119">La clase es un atributo que requiere la búsqueda en tiempo de ejecución muy rápido.</span><span class="sxs-lookup"><span data-stu-id="051c9-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="051c9-120">Atributos sellados tienen ligeramente más altos niveles de rendimiento a que no sellados.</span><span class="sxs-lookup"><span data-stu-id="051c9-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="051c9-121">vea [atributos](../../../docs/standard/design-guidelines/attributes.md).</span><span class="sxs-lookup"><span data-stu-id="051c9-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="051c9-122">**X DO NOT** declarar miembros protegidos o virtuales en tipos sealed.</span><span class="sxs-lookup"><span data-stu-id="051c9-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="051c9-123">Por definición, no se puede heredar de tipos sealed de.</span><span class="sxs-lookup"><span data-stu-id="051c9-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="051c9-124">Esto significa que no se puede llamar a miembros protegidos en tipos sealed, y no se puede invalidar métodos virtuales en tipos sealed.</span><span class="sxs-lookup"><span data-stu-id="051c9-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="051c9-125">**Considere la posibilidad de ✓** sellar los miembros reemplazados.</span><span class="sxs-lookup"><span data-stu-id="051c9-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="051c9-126">Problemas que pueden derivarse de introducción a los miembros virtuales (se describe en [miembros virtuales](../../../docs/standard/design-guidelines/virtual-members.md)) se aplican a invalidaciones, aunque a ligeramente menor grado.</span><span class="sxs-lookup"><span data-stu-id="051c9-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="051c9-127">Sellar una invalidación intercepta estos problemas desde ese punto en la jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="051c9-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="051c9-128">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="051c9-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="051c9-129">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="051c9-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051c9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="051c9-130">See Also</span></span>  
 [<span data-ttu-id="051c9-131">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="051c9-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="051c9-132">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="051c9-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="051c9-133">Clases no selladas</span><span class="sxs-lookup"><span data-stu-id="051c9-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
