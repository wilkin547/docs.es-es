---
title: Diseño de interfaces
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dea5877f952869d5c84d6019617fcdc52d8ee0a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573044"
---
# <a name="interface-design"></a><span data-ttu-id="0cd6b-102">Diseño de interfaces</span><span class="sxs-lookup"><span data-stu-id="0cd6b-102">Interface Design</span></span>
<span data-ttu-id="0cd6b-103">Aunque la mayoría de las API se modela mejor mediante las clases y structs, hay casos en los que interfaces son más adecuadas o son la única opción.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="0cd6b-104">El CLR no admite la herencia múltiple (es decir, las clases CLR no pueden heredar de más de una clase base), pero permite tipos para implementar una o más interfaces además de heredar de una clase base.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="0cd6b-105">Por lo tanto, las interfaces se utilizan a menudo para lograr el efecto de herencia múltiple.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="0cd6b-106">Por ejemplo, <xref:System.IDisposable> es una interfaz que permite que los tipos admitir disposability independiente de cualquier otra jerarquía de herencia en el que desean participar.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="0cd6b-107">Es la situación en que definir una interfaz es adecuada en la creación de una interfaz común que puede ser compatible con varios tipos, incluidos algunos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="0cd6b-108">Tipos de valor no pueden heredar de tipos distintos de <xref:System.ValueType>, pero pueden implementar interfaces, por lo que usar una interfaz es la única opción para proporcionar un tipo base común.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="0cd6b-109">**✓ DO** defina una interfaz si necesita algunas API comunes que deben admitir un conjunto de tipos que incluye los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="0cd6b-110">**✓ CONSIDER** define una interfaz si necesita admitir su funcionalidad en tipos que ya heredan de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="0cd6b-111">**X AVOID** mediante las interfaces de marcador (interfaces sin miembros).</span><span class="sxs-lookup"><span data-stu-id="0cd6b-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="0cd6b-112">Si necesita marcar una clase como si tuviera una característica específica (marcador), por lo general, utilice un atributo personalizado en lugar de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="0cd6b-113">**✓ DO** proporcionar al menos un tipo que es una implementación de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="0cd6b-114">Haciendo esto ayuda a validar el diseño de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="0cd6b-115">Por ejemplo, <xref:System.Collections.Generic.List%601> es una implementación de la <xref:System.Collections.Generic.IList%601> interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="0cd6b-116">**✓ DO** proporcionan al menos una API que consuma cada interfaz definida (un método que toma la interfaz como un parámetro o una propiedad con tipo como la interfaz).</span><span class="sxs-lookup"><span data-stu-id="0cd6b-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="0cd6b-117">Haciendo esto ayuda a validar el diseño de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="0cd6b-118">Por ejemplo, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consume el <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="0cd6b-119">**X DO NOT** agregar miembros a una interfaz que se haya distribuido previamente.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="0cd6b-120">Si lo hace, se interrumpiría las implementaciones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="0cd6b-121">Debe crear una nueva interfaz con el fin de evitar problemas de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="0cd6b-122">Excepto en los casos descritos en estas instrucciones, por lo general, debe, elegir las clases en lugar de interfaces diseñar bibliotecas reutilizables de código administrado.</span><span class="sxs-lookup"><span data-stu-id="0cd6b-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="0cd6b-123">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="0cd6b-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0cd6b-124">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0cd6b-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd6b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cd6b-125">See Also</span></span>  
 [<span data-ttu-id="0cd6b-126">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="0cd6b-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="0cd6b-127">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0cd6b-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
