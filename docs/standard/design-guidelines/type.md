---
title: Instrucciones de diseño de tipos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 53c7bccd4afb92e6afcaccf4b1c50c41f574fedb
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="type-design-guidelines"></a><span data-ttu-id="6d3d0-102">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="6d3d0-102">Type Design Guidelines</span></span>
<span data-ttu-id="6d3d0-103">Desde la perspectiva CLR, hay solo dos categorías de tipos: tipos de referencia y tipos de valor, pero con el fin de obtener una explicación sobre el diseño de marco de trabajo, se dividen los tipos en grupos lógicos más, cada uno con sus propias reglas de diseño específicas.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="6d3d0-104">Las clases son el caso general de los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="6d3d0-105">Constituyen la mayor parte de los tipos en la mayoría de los marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="6d3d0-106">Clases pendientes a su popularidad, para el conjunto de características orientadas a objetos que admiten datos completos y su aplicabilidad general.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="6d3d0-107">Clases base y clases abstractas son grupos lógicos especiales relacionadas con la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="6d3d0-108">Interfaces son tipos que pueden ser implementados por los tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="6d3d0-109">Por lo tanto pueden servir como raíces de polimórficas jerarquías de tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="6d3d0-110">Además, se pueden utilizar interfaces para simular la herencia múltiple, que no es compatible de forma nativa con CLR.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="6d3d0-111">Las estructuras son el caso general de los tipos de valor y que debe reservarse para los tipos pequeños y sencillos, como primitivas del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="6d3d0-112">Las enumeraciones son un caso especial de tipos de valor utilizados para definir cortos conjuntos de valores, como los días de la semana, los colores de consola y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="6d3d0-113">Las clases estáticas son tipos que pretende ser contenedores para los miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="6d3d0-114">Se suelen usar para proporcionar accesos directos a otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="6d3d0-115">Delegados, excepciones, atributos, matrices y colecciones son todos los casos especiales de los tipos de referencia diseñados para usos específicos, y directrices de diseño y de uso se tratan en otro lugar en este libro.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="6d3d0-116">**✓ HACER** Asegúrese de que cada tipo es un conjunto bien definido de miembros relacionados, no sólo un conjunto aleatorio de funcionalidad no relacionado.</span><span class="sxs-lookup"><span data-stu-id="6d3d0-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d3d0-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d3d0-117">In This Section</span></span>  
 [<span data-ttu-id="6d3d0-118">Elección entre clase y estructura</span><span class="sxs-lookup"><span data-stu-id="6d3d0-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="6d3d0-119">Diseño de clases abstractas</span><span class="sxs-lookup"><span data-stu-id="6d3d0-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="6d3d0-120">Diseño de clases estáticas</span><span class="sxs-lookup"><span data-stu-id="6d3d0-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="6d3d0-121">Diseño de interfaces</span><span class="sxs-lookup"><span data-stu-id="6d3d0-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="6d3d0-122">Diseño de estructuras</span><span class="sxs-lookup"><span data-stu-id="6d3d0-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="6d3d0-123">Diseño de enumeraciones</span><span class="sxs-lookup"><span data-stu-id="6d3d0-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="6d3d0-124">Tipos anidados</span><span class="sxs-lookup"><span data-stu-id="6d3d0-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="6d3d0-125">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6d3d0-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6d3d0-126">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6d3d0-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3d0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d3d0-127">See Also</span></span>  
 [<span data-ttu-id="6d3d0-128">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d3d0-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
