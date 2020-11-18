---
title: Instrucciones de diseño de .NET Framework
description: Vea directrices de diseño del marco para diseñar bibliotecas que extienden e interactúan con .NET, para garantizar la coherencia de la API y la facilidad de uso.
titleSuffix: ''
ms.date: 10/22/2008
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 9dc764492e1ac565c51d49d07e6566295bb76bc1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821039"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="9dbf1-103">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9dbf1-103">Framework Design Guidelines</span></span>
<span data-ttu-id="9dbf1-104">En esta sección se proporcionan instrucciones para diseñar bibliotecas que extienden e interactúan con el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-104">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="9dbf1-105">El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y la facilidad de uso, ya que proporciona un modelo de programación unificado que es independiente del lenguaje de programación usado para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-105">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="9dbf1-106">Se recomienda seguir estas directrices de diseño al desarrollar clases y componentes que extienden el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-106">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="9dbf1-107">El diseño incoherente de la biblioteca afecta negativamente a la productividad del desarrollador y desaconseja la adopción.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-107">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="9dbf1-108">Las instrucciones se organizan como recomendaciones sencillas precedidas de los términos `Do` ,, `Consider` `Avoid` y `Do not` .</span><span class="sxs-lookup"><span data-stu-id="9dbf1-108">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="9dbf1-109">Estas instrucciones están diseñadas para ayudar a los diseñadores de biblioteca de clases a comprender las ventajas e inconvenientes entre las distintas soluciones.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-109">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="9dbf1-110">Puede haber situaciones en las que el diseño de la biblioteca sea adecuado, ya que se infringen estas directrices de diseño.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-110">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="9dbf1-111">Estos casos deben ser raros y es importante que tenga una razón clara y convincente para su decisión.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-111">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="9dbf1-112">Estas instrucciones se exforman de las *directrices de diseño de marcos de libros: convenciones, expresiones y patrones para bibliotecas de .net reutilizables, 2ª edición*, por Krzysztof Cwalina y Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-112">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9dbf1-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9dbf1-113">In This Section</span></span>  
 [<span data-ttu-id="9dbf1-114">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="9dbf1-114">Naming Guidelines</span></span>](naming-guidelines.md)  
 <span data-ttu-id="9dbf1-115">Proporciona instrucciones para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros de las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-115">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="9dbf1-116">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="9dbf1-116">Type Design Guidelines</span></span>](type.md)  
 <span data-ttu-id="9dbf1-117">Proporciona instrucciones para el uso de clases, interfaces, enumeraciones, estructuras y otros tipos estáticos y abstractos.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-117">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="9dbf1-118">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="9dbf1-118">Member Design Guidelines</span></span>](member.md)  
 <span data-ttu-id="9dbf1-119">Proporciona instrucciones para diseñar y usar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-119">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="9dbf1-120">Diseñar extensibilidad</span><span class="sxs-lookup"><span data-stu-id="9dbf1-120">Designing for Extensibility</span></span>](designing-for-extensibility.md)  
 <span data-ttu-id="9dbf1-121">Describe los mecanismos de extensibilidad, como las subclases, el uso de eventos, miembros virtuales y devoluciones de llamada, y explica cómo elegir los mecanismos que mejor satisfagan los requisitos de su marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-121">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="9dbf1-122">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="9dbf1-122">Design Guidelines for Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="9dbf1-123">Describe las directrices de diseño para diseñar, iniciar y detectar excepciones.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-123">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="9dbf1-124">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="9dbf1-124">Usage Guidelines</span></span>](usage-guidelines.md)  
 <span data-ttu-id="9dbf1-125">Describe las instrucciones para usar tipos comunes como matrices, atributos y colecciones, la compatibilidad con la serialización y la sobrecarga de operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-125">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="9dbf1-126">Modelos de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="9dbf1-126">Common Design Patterns</span></span>](common-design-patterns.md)  
 <span data-ttu-id="9dbf1-127">Proporciona instrucciones para elegir e implementar propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="9dbf1-127">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="9dbf1-128">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="9dbf1-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9dbf1-129">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="9dbf1-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbf1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dbf1-130">See also</span></span>

- [<span data-ttu-id="9dbf1-131">Información general</span><span class="sxs-lookup"><span data-stu-id="9dbf1-131">Overview</span></span>](../../framework/get-started/overview.md)
- [<span data-ttu-id="9dbf1-132">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="9dbf1-132">Development Guide</span></span>](../../framework/development-guide.md)
