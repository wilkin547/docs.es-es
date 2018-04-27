---
title: Instrucciones de diseño de .NET Framework
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c54ec4a5cc3c4bef1e6460b2c9971af4e2af983a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="f7d56-102">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7d56-102">Framework Design Guidelines</span></span>
<span data-ttu-id="f7d56-103">Esta sección proporciona instrucciones de diseño de las bibliotecas que extensión e interactúan con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7d56-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="f7d56-104">El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y facilidad de uso al proporcionar un modelo de programación unificado que es independiente del lenguaje de programación utilizado para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f7d56-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="f7d56-105">Se recomienda seguir estas directrices de diseño al desarrollar clases y componentes que extienden .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7d56-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="f7d56-106">Diseño de biblioteca incoherente afecta negativamente afecta a la productividad del desarrollador y desaconseja adopción.</span><span class="sxs-lookup"><span data-stu-id="f7d56-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="f7d56-107">Las instrucciones se organizan como recomendaciones sencillas precedidas con los términos de `Do`, `Consider`, `Avoid`, y `Do not`.</span><span class="sxs-lookup"><span data-stu-id="f7d56-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="f7d56-108">Estas instrucciones están diseñadas para ayudar a los diseñadores de la biblioteca de clases a comprender las ventajas y desventajas de las distintas soluciones.</span><span class="sxs-lookup"><span data-stu-id="f7d56-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="f7d56-109">Puede haber situaciones donde buen diseño de bibliotecas requiere que infringen estas directrices de diseño.</span><span class="sxs-lookup"><span data-stu-id="f7d56-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="f7d56-110">Estos casos deben ser infrecuentes, y es importante que tenga una razón clara de peso para su decisión.</span><span class="sxs-lookup"><span data-stu-id="f7d56-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="f7d56-111">Estas instrucciones se ha extraído de la libreta de *directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición*, Krzysztof Cwalina y Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="f7d56-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7d56-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f7d56-112">In This Section</span></span>  
 [<span data-ttu-id="f7d56-113">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="f7d56-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="f7d56-114">Proporciona instrucciones para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros en bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="f7d56-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="f7d56-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="f7d56-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="f7d56-116">Proporciona instrucciones para utilizar clases estáticas y abstractas, interfaces, enumeraciones, estructuras y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="f7d56-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="f7d56-117">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="f7d56-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="f7d56-118">Proporciona directrices para diseñar y utilizar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="f7d56-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="f7d56-119">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="f7d56-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="f7d56-120">Describe los mecanismos de extensibilidad, como crear subclases de una, con eventos, los miembros virtuales y las devoluciones de llamada y explica cómo elegir los mecanismos que mejor cumplen los requisitos del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f7d56-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="f7d56-121">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="f7d56-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="f7d56-122">Describe las instrucciones de diseño para diseñar, producir y detectar excepciones.</span><span class="sxs-lookup"><span data-stu-id="f7d56-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="f7d56-123">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="f7d56-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="f7d56-124">Describe las instrucciones para utilizar tipos comunes, como matrices, atributos y colecciones, admita la serialización y la sobrecarga de operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="f7d56-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="f7d56-125">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="f7d56-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="f7d56-126">Proporciona directrices para elegir e implementar propiedades de dependencia y el patrón de dispose.</span><span class="sxs-lookup"><span data-stu-id="f7d56-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="f7d56-127">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="f7d56-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f7d56-128">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f7d56-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d56-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7d56-129">See Also</span></span>  
 [<span data-ttu-id="f7d56-130">Información general</span><span class="sxs-lookup"><span data-stu-id="f7d56-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="f7d56-131">Guía básica de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7d56-131">Roadmap for the .NET Framework</span></span>](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="f7d56-132">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="f7d56-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
