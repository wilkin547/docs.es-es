---
title: Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 89e892a379c7540cf67488471ae5281a4c4b86f4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="attributes"></a><span data-ttu-id="b7191-102">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7191-102">Attributes</span></span>
<span data-ttu-id="b7191-103"><xref:System.Attribute?displayProperty=nameWithType>es una clase base que se utiliza para definir atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b7191-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="b7191-104">Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros.</span><span class="sxs-lookup"><span data-stu-id="b7191-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="b7191-105">Que se almacenan en los metadatos del ensamblado y se pueden tener acceso en tiempo de ejecución mediante las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="b7191-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="b7191-106">Por ejemplo, el marco de trabajo define la <xref:System.ObsoleteAttribute>, que pueden aplicarse a un tipo o miembro para indicar que el tipo o miembro está en desuso.</span><span class="sxs-lookup"><span data-stu-id="b7191-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="b7191-107">Atributos pueden tener una o varias propiedades que transportan datos adicionales relacionados con el atributo.</span><span class="sxs-lookup"><span data-stu-id="b7191-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="b7191-108">Por ejemplo, `ObsoleteAttribute` podría incluir información adicional acerca de la versión en que un tipo o miembro se obtuvo en desuso y la descripción de las nuevas API reemplazando la API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="b7191-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="b7191-109">Algunas propiedades de un atributo deben especificarse cuando se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="b7191-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="b7191-110">Estos se conocen como las propiedades necesarias o argumentos necesarios, ya que se representan como parámetros posicionales constructor.</span><span class="sxs-lookup"><span data-stu-id="b7191-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="b7191-111">Por ejemplo, el <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de la <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.</span><span class="sxs-lookup"><span data-stu-id="b7191-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="b7191-112">Las propiedades que no necesariamente deben especificarse cuando se aplica el atributo se denominan propiedades opcionales (o argumentos opcionales).</span><span class="sxs-lookup"><span data-stu-id="b7191-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="b7191-113">Dichas reglas se representan mediante propiedades configurables.</span><span class="sxs-lookup"><span data-stu-id="b7191-113">They are represented by settable properties.</span></span> <span data-ttu-id="b7191-114">Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo.</span><span class="sxs-lookup"><span data-stu-id="b7191-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="b7191-115">Por ejemplo, el <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> propiedad representa un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="b7191-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="b7191-116">**✓ HACER** nombres de las clases de atributo personalizado con el sufijo "Atributos".</span><span class="sxs-lookup"><span data-stu-id="b7191-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="b7191-117">**✓ HACER** aplicar el <xref:System.AttributeUsageAttribute> a atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b7191-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="b7191-118">**✓ HACER** proporcionar propiedades configurables para los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b7191-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="b7191-119">**✓ HACER** proporcionan propiedades get-only de argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="b7191-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="b7191-120">**✓ HACER** proporcionan parámetros de constructor para inicializar las propiedades que corresponden a los argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="b7191-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="b7191-121">Cada parámetro debe tener el mismo nombre (aunque con distintas mayúsculas y minúsculas) como la propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b7191-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="b7191-122">**X evitar** proporcionar parámetros del constructor para inicializar las propiedades que corresponden a los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b7191-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="b7191-123">En otras palabras, no tiene propiedades que se pueden establecer con un constructor y un establecedor.</span><span class="sxs-lookup"><span data-stu-id="b7191-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="b7191-124">Esta instrucción hace muy explícitas qué argumentos son opcionales y que son necesarios y evita la necesidad de dos maneras de hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="b7191-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="b7191-125">**X evitar** sobrecarga de constructores de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b7191-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="b7191-126">Tener solo un constructor claramente comunica con el usuario que los argumentos son obligatorios y cuáles son opcionales.</span><span class="sxs-lookup"><span data-stu-id="b7191-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="b7191-127">**✓ HACER** sellar clases de atributos personalizados, si es posible.</span><span class="sxs-lookup"><span data-stu-id="b7191-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="b7191-128">Esto acelera la búsqueda para el atributo.</span><span class="sxs-lookup"><span data-stu-id="b7191-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="b7191-129">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="b7191-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b7191-130">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b7191-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7191-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7191-131">See Also</span></span>  
 [<span data-ttu-id="b7191-132">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7191-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="b7191-133">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="b7191-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
