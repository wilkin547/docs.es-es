---
description: 'Más información acerca de: Atributos'
title: Atributos
ms.date: 10/22/2008
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
ms.openlocfilehash: 1557ba0945da0c8498c67f70ba4a01dd0bbe432e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642427"
---
# <a name="attributes"></a><span data-ttu-id="f50f1-103">Atributos</span><span class="sxs-lookup"><span data-stu-id="f50f1-103">Attributes</span></span>

<span data-ttu-id="f50f1-104"><xref:System.Attribute?displayProperty=nameWithType> es una clase base que se usa para definir atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f50f1-104"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>

 <span data-ttu-id="f50f1-105">Los atributos son anotaciones que se pueden agregar a elementos de programación como ensamblados, tipos, miembros y parámetros.</span><span class="sxs-lookup"><span data-stu-id="f50f1-105">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="f50f1-106">Se almacenan en los metadatos del ensamblado y se puede tener acceso a ellos en tiempo de ejecución mediante las API de reflexión.</span><span class="sxs-lookup"><span data-stu-id="f50f1-106">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="f50f1-107">Por ejemplo, el marco define el atributo <xref:System.ObsoleteAttribute>, que se puede aplicar a un tipo o un miembro para indicar que el tipo o miembro está en desuso.</span><span class="sxs-lookup"><span data-stu-id="f50f1-107">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>

 <span data-ttu-id="f50f1-108">Los atributos pueden tener una o varias propiedades que contienen datos adicionales relacionados con el atributo.</span><span class="sxs-lookup"><span data-stu-id="f50f1-108">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="f50f1-109">Por ejemplo, `ObsoleteAttribute` podría incluir información adicional sobre en qué versión un tipo o un miembro quedó en desuso, así como la descripción de las nuevas API que reemplazan a la API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="f50f1-109">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>

 <span data-ttu-id="f50f1-110">Se deben especificar algunas propiedades de un atributo cuando se aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="f50f1-110">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="f50f1-111">Estas se conocen como "propiedades requeridas" o "argumentos necesarios", porque se representan como parámetros del constructor posicional.</span><span class="sxs-lookup"><span data-stu-id="f50f1-111">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="f50f1-112">Por ejemplo, la propiedad <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> del atributo <xref:System.Diagnostics.ConditionalAttribute> es una propiedad obligatoria.</span><span class="sxs-lookup"><span data-stu-id="f50f1-112">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>

 <span data-ttu-id="f50f1-113">Las propiedades que no tienen que especificarse necesariamente cuando se aplica el atributo se denominan "propiedades opcionales" (o "argumentos opcionales").</span><span class="sxs-lookup"><span data-stu-id="f50f1-113">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="f50f1-114">Se representan mediante propiedades que se pueden establecer.</span><span class="sxs-lookup"><span data-stu-id="f50f1-114">They are represented by settable properties.</span></span> <span data-ttu-id="f50f1-115">Los compiladores proporcionan una sintaxis especial para establecer estas propiedades cuando se aplica un atributo.</span><span class="sxs-lookup"><span data-stu-id="f50f1-115">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="f50f1-116">Por ejemplo, la propiedad <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> representa un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="f50f1-116">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>

 <span data-ttu-id="f50f1-117">✔️ Asigne un nombre a las clases de atributos personalizados con el sufijo "Attribute".</span><span class="sxs-lookup"><span data-stu-id="f50f1-117">✔️ DO name custom attribute classes with the suffix "Attribute."</span></span>

 <span data-ttu-id="f50f1-118">✔️ Aplique el atributo <xref:System.AttributeUsageAttribute> a los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f50f1-118">✔️ DO apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>

 <span data-ttu-id="f50f1-119">✔️ Proporcione propiedades que se pueden establecer para los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="f50f1-119">✔️ DO provide settable properties for optional arguments.</span></span>

 <span data-ttu-id="f50f1-120">✔️ Proporcione propiedades get-only para los argumentos requeridos.</span><span class="sxs-lookup"><span data-stu-id="f50f1-120">✔️ DO provide get-only properties for required arguments.</span></span>

 <span data-ttu-id="f50f1-121">✔️ Proporcione parámetros de constructor para inicializar las propiedades correspondientes a los argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="f50f1-121">✔️ DO provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="f50f1-122">Cada parámetro debe tener el mismo nombre (aunque con distinto uso de mayúsculas y minúsculas) que la propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f50f1-122">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>

 <span data-ttu-id="f50f1-123">❌ EVITE proporcionar parámetros de constructor para inicializar las propiedades correspondientes a los argumentos opcionales.</span><span class="sxs-lookup"><span data-stu-id="f50f1-123">❌ AVOID providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>

 <span data-ttu-id="f50f1-124">En otras palabras, no tenga propiedades que se puedan establecer con un constructor y un establecedor.</span><span class="sxs-lookup"><span data-stu-id="f50f1-124">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="f50f1-125">Esta instrucción consigue que resulte evidente qué argumentos son opcionales y cuáles necesarios, y evita tener dos formas de hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="f50f1-125">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>

 <span data-ttu-id="f50f1-126">❌ EVITE sobrecargar los constructores de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f50f1-126">❌ AVOID overloading custom attribute constructors.</span></span>

 <span data-ttu-id="f50f1-127">Tener un solo constructor comunica claramente al usuario qué argumentos son obligatorios y cuáles opcionales.</span><span class="sxs-lookup"><span data-stu-id="f50f1-127">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>

 <span data-ttu-id="f50f1-128">✔️ Selle las clases de atributos personalizados, si es posible.</span><span class="sxs-lookup"><span data-stu-id="f50f1-128">✔️ DO seal custom attribute classes, if possible.</span></span> <span data-ttu-id="f50f1-129">De esta forma, la búsqueda de atributos será más rápida.</span><span class="sxs-lookup"><span data-stu-id="f50f1-129">This makes the look-up for the attribute faster.</span></span>

 <span data-ttu-id="f50f1-130">*Portions &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="f50f1-130">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f50f1-131">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="f50f1-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f50f1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f50f1-132">See also</span></span>

- [<span data-ttu-id="f50f1-133">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f50f1-133">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="f50f1-134">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="f50f1-134">Usage Guidelines</span></span>](usage-guidelines.md)
