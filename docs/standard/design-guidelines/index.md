---
title: Instrucciones de diseño de .NET Framework
titleSuffix: ''
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
ms.openlocfilehash: 8abe64476a5d3d1319dfa30dd7a06dc2bb541a0f
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904612"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="2728f-102">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2728f-102">Framework Design Guidelines</span></span>
<span data-ttu-id="2728f-103">En esta sección se proporcionan instrucciones para diseñar bibliotecas que extienden e interactúan con el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2728f-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="2728f-104">El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y la facilidad de uso, ya que proporciona un modelo de programación unificado que es independiente del lenguaje de programación usado para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="2728f-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="2728f-105">Se recomienda seguir estas directrices de diseño al desarrollar clases y componentes que extienden el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2728f-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="2728f-106">El diseño incoherente de la biblioteca afecta negativamente a la productividad del desarrollador y desaconseja la adopción.</span><span class="sxs-lookup"><span data-stu-id="2728f-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="2728f-107">Las instrucciones se organizan como recomendaciones sencillas precedidas de los términos `Do`, `Consider`, `Avoid`y `Do not`.</span><span class="sxs-lookup"><span data-stu-id="2728f-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="2728f-108">Estas instrucciones están diseñadas para ayudar a los diseñadores de biblioteca de clases a comprender las ventajas e inconvenientes entre las distintas soluciones.</span><span class="sxs-lookup"><span data-stu-id="2728f-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="2728f-109">Puede haber situaciones en las que el diseño de la biblioteca sea adecuado, ya que se infringen estas directrices de diseño.</span><span class="sxs-lookup"><span data-stu-id="2728f-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="2728f-110">Estos casos deben ser raros y es importante que tenga una razón clara y convincente para su decisión.</span><span class="sxs-lookup"><span data-stu-id="2728f-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="2728f-111">Estas instrucciones se exforman de las *directrices de diseño de marcos de libros: convenciones, expresiones y patrones para bibliotecas de .net reutilizables, 2ª edición*, por Krzysztof Cwalina y Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="2728f-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2728f-112">Esta sección</span><span class="sxs-lookup"><span data-stu-id="2728f-112">In This Section</span></span>  
 [<span data-ttu-id="2728f-113">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="2728f-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="2728f-114">Proporciona instrucciones para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros de las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="2728f-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="2728f-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="2728f-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="2728f-116">Proporciona instrucciones para el uso de clases, interfaces, enumeraciones, estructuras y otros tipos estáticos y abstractos.</span><span class="sxs-lookup"><span data-stu-id="2728f-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="2728f-117">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="2728f-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="2728f-118">Proporciona instrucciones para diseñar y usar propiedades, métodos, constructores, campos, eventos, operadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="2728f-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="2728f-119">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="2728f-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="2728f-120">Describe los mecanismos de extensibilidad, como las subclases, el uso de eventos, miembros virtuales y devoluciones de llamada, y explica cómo elegir los mecanismos que mejor satisfagan los requisitos de su marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2728f-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="2728f-121">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="2728f-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="2728f-122">Describe las directrices de diseño para diseñar, iniciar y detectar excepciones.</span><span class="sxs-lookup"><span data-stu-id="2728f-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="2728f-123">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="2728f-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="2728f-124">Describe las instrucciones para usar tipos comunes como matrices, atributos y colecciones, la compatibilidad con la serialización y la sobrecarga de operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="2728f-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="2728f-125">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="2728f-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="2728f-126">Proporciona instrucciones para elegir e implementar propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="2728f-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="2728f-127">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="2728f-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2728f-128">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="2728f-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2728f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2728f-129">See also</span></span>

- [<span data-ttu-id="2728f-130">Información general</span><span class="sxs-lookup"><span data-stu-id="2728f-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="2728f-131">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="2728f-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
