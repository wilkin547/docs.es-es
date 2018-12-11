---
title: Attributes1
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 7ab499d5a9c8388e9081a07921d3e444c0cdd879
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131435"
---
# <a name="attributes"></a><span data-ttu-id="e471a-102">Atributos</span><span class="sxs-lookup"><span data-stu-id="e471a-102">Attributes</span></span>
<span data-ttu-id="e471a-103"><xref:System.Attribute?displayProperty=nameWithType> se utiliza una clase base para definir atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e471a-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="e471a-104">Los atributos son anotaciones que pueden agregarse a elementos de programación como ensamblados, tipos, miembros y parámetros.</span><span class="sxs-lookup"><span data-stu-id="e471a-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="e471a-105">Que se almacenan en los metadatos del ensamblado y se pueden tener acceso en tiempo de ejecución mediante las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="e471a-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="e471a-106">Por ejemplo, el marco de trabajo define el <xref:System.ObsoleteAttribute>, que pueden aplicarse a un tipo o miembro para indicar que el tipo o miembro en desuso.</span><span class="sxs-lookup"><span data-stu-id="e471a-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="e471a-107">Los atributos pueden tener una o varias propiedades que transportan datos adicionales relacionados con el atributo.</span><span class="sxs-lookup"><span data-stu-id="e471a-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="e471a-108">Por ejemplo, `ObsoleteAttribute` podría incluir información adicional sobre la versión en que un tipo o miembro se obtuvo en desuso y la descripción de las nuevas API reemplazando la API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="e471a-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="e471a-109">Algunas propiedades de un atributo se deben especificar cuando se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="e471a-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="e471a-110">Estos se conocen como las propiedades necesarias o los argumentos necesarios, ya que se representan como parámetros de constructor posicional.</span><span class="sxs-lookup"><span data-stu-id="e471a-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="e471a-111">Por ejemplo, el <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> propiedad de la <xref:System.Diagnostics.ConditionalAttribute> es una propiedad necesaria.</span><span class="sxs-lookup"><span data-stu-id="e471a-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="e471a-112">Las propiedades que no necesariamente deben especificarse cuando se aplica el atributo se denominan propiedades opcionales (o argumentos opcionales).</span><span class="sxs-lookup"><span data-stu-id="e471a-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="e471a-113">Se representan mediante las propiedades configurables.</span><span class="sxs-lookup"><span data-stu-id="e471a-113">They are represented by settable properties.</span></span> <span data-ttu-id="e471a-114">Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo.</span><span class="sxs-lookup"><span data-stu-id="e471a-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="e471a-115">Por ejemplo, el <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> propiedad representa un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="e471a-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="e471a-116">**✓ DO** nombres de las clases de atributo personalizado con el sufijo "Atributos".</span><span class="sxs-lookup"><span data-stu-id="e471a-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="e471a-117">**✓ DO** aplicar el <xref:System.AttributeUsageAttribute> a atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e471a-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="e471a-118">**✓ DO** proporcionar propiedades configurables para los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="e471a-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="e471a-119">**✓ DO** proporcionan propiedades get-only de argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="e471a-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="e471a-120">**✓ DO** proporcionan parámetros de constructor para inicializar las propiedades que corresponden a los argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="e471a-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="e471a-121">Cada parámetro debe tener el mismo nombre (aunque con distinguen mayúsculas de minúsculas) como la propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e471a-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="e471a-122">**X AVOID** proporcionar parámetros del constructor para inicializar las propiedades que corresponden a los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="e471a-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="e471a-123">En otras palabras, no tiene propiedades que se pueden establecer con un constructor y un establecedor.</span><span class="sxs-lookup"><span data-stu-id="e471a-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="e471a-124">Esta instrucción hace que sea muy explícito que los argumentos son opcionales y que son necesarias y evita tener dos formas de hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="e471a-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="e471a-125">**X AVOID** sobrecarga de constructores de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="e471a-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="e471a-126">Tener solo un constructor claramente comunica al usuario qué argumentos son obligatorios y cuáles son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e471a-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="e471a-127">**✓ DO** sellar clases de atributos personalizados, si es posible.</span><span class="sxs-lookup"><span data-stu-id="e471a-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="e471a-128">Esto hace que la búsqueda para el atributo con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="e471a-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="e471a-129">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="e471a-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e471a-130">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e471a-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e471a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e471a-131">See also</span></span>

- [<span data-ttu-id="e471a-132">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e471a-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="e471a-133">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="e471a-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
