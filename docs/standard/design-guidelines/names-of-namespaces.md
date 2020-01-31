---
title: Nombres de espacios de nombres
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 52fee0dfaff284c2c1a6afcb8aa7530c28a60d65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744140"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="dca68-102">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="dca68-102">Names of Namespaces</span></span>
<span data-ttu-id="dca68-103">Como ocurre con otras directrices de nomenclatura, el objetivo de asignar nombres a los espacios de nombres es crear una claridad suficiente para que el programador use el marco de trabajo para saber inmediatamente cuál es el contenido del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="dca68-104">La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="dca68-104">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="dca68-105">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dca68-105">The following are examples:</span></span>

 <span data-ttu-id="dca68-106">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="dca68-106">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="dca68-107">✔️ prefijar los nombres de los espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas empresas tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="dca68-107">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="dca68-108">✔️ usar un nombre de producto estable y independiente de la versión en el segundo nivel de un nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-108">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="dca68-109">❌ no usan jerarquías organizativas como base para los nombres de las jerarquías de espacio de nombres, ya que los nombres de grupo dentro de las organizaciones tienden a ser de corta duración.</span><span class="sxs-lookup"><span data-stu-id="dca68-109">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="dca68-110">Organice la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.</span><span class="sxs-lookup"><span data-stu-id="dca68-110">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="dca68-111">✔️ usar PascalCasing y separar los componentes de espacio de nombres con puntos (por ejemplo, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="dca68-111">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="dca68-112">Si la marca emplea una grafía no tradicional, debe seguir las mayúsculas y minúsculas definidas por la marca, incluso si se desvía de la grafía normal del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-112">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="dca68-113">✔️ CONSIDERE el uso de nombres de espacios de nombres plurales cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="dca68-113">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="dca68-114">Por ejemplo, use `System.Collections` en lugar de `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="dca68-114">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="dca68-115">Sin embargo, los nombres de marca y los acrónimos son excepciones a esta regla.</span><span class="sxs-lookup"><span data-stu-id="dca68-115">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="dca68-116">Por ejemplo, use `System.IO` en lugar de `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="dca68-116">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="dca68-117">❌ no utilizan el mismo nombre para un espacio de nombres y un tipo en dicho espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-117">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="dca68-118">Por ejemplo, no use `Debug` como nombre de espacio de nombres y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-118">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="dca68-119">Varios compiladores requieren que estos tipos sean completos.</span><span class="sxs-lookup"><span data-stu-id="dca68-119">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="dca68-120">Conflictos de nombres de tipos y espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="dca68-120">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="dca68-121">❌ no presentan nombres de tipo genérico como `Element`, `Node`, `Log`y `Message`.</span><span class="sxs-lookup"><span data-stu-id="dca68-121">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="dca68-122">Existe una probabilidad muy alta de que esto provocará conflictos de nombres de tipo en escenarios comunes.</span><span class="sxs-lookup"><span data-stu-id="dca68-122">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="dca68-123">Debe calificar los nombres de tipo genérico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="dca68-123">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="dca68-124">Existen directrices específicas para evitar conflictos de nombres de tipo para distintas categorías de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="dca68-124">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="dca68-125">**Espacios de nombres del modelo de aplicación**</span><span class="sxs-lookup"><span data-stu-id="dca68-125">**Application model namespaces**</span></span>

     <span data-ttu-id="dca68-126">Los espacios de nombres que pertenecen a un único modelo de aplicación suelen usarse juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dca68-126">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="dca68-127">Por ejemplo, el espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> se usa muy rara vez junto con el espacio de nombres <xref:System.Web.UI?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dca68-127">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="dca68-128">A continuación se muestra una lista de grupos de espacios de nombres del modelo de aplicación conocidos:</span><span class="sxs-lookup"><span data-stu-id="dca68-128">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="dca68-129">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="dca68-129">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="dca68-130">❌ no proporcionan el mismo nombre a los tipos de los espacios de nombres dentro de un único modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dca68-130">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="dca68-131">Por ejemplo, no agregue un tipo denominado `Page` al espacio de nombres <xref:System.Web.UI.Adapters?displayProperty=nameWithType>, porque el espacio de nombres <xref:System.Web.UI?displayProperty=nameWithType> ya contiene un tipo denominado `Page`.</span><span class="sxs-lookup"><span data-stu-id="dca68-131">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="dca68-132">**Espacios de nombres de infraestructura**</span><span class="sxs-lookup"><span data-stu-id="dca68-132">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="dca68-133">Este grupo contiene espacios de nombres que rara vez se importan durante el desarrollo de aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="dca68-133">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="dca68-134">Por ejemplo, los espacios de nombres `.Design` se usan principalmente al desarrollar herramientas de programación.</span><span class="sxs-lookup"><span data-stu-id="dca68-134">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="dca68-135">Evitar conflictos con tipos en estos espacios de nombres no es crítico.</span><span class="sxs-lookup"><span data-stu-id="dca68-135">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="dca68-136">**Espacios de nombres principales**</span><span class="sxs-lookup"><span data-stu-id="dca68-136">**Core namespaces**</span></span>

     <span data-ttu-id="dca68-137">Los espacios de nombres principales incluyen todos los espacios de `System`, excluidos los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="dca68-137">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="dca68-138">Los espacios de nombres principales incluyen, entre otros, `System`, `System.IO`, `System.Xml`y `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="dca68-138">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="dca68-139">❌ no proporcionan nombres de tipos que pudieran entrar en conflicto con cualquier tipo de los espacios de nombres principales.</span><span class="sxs-lookup"><span data-stu-id="dca68-139">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="dca68-140">Por ejemplo, nunca use `Stream` como un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="dca68-140">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="dca68-141">Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo de uso muy frecuente.</span><span class="sxs-lookup"><span data-stu-id="dca68-141">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="dca68-142">**Grupos de espacios de nombres de tecnología**</span><span class="sxs-lookup"><span data-stu-id="dca68-142">**Technology namespace groups**</span></span>

     <span data-ttu-id="dca68-143">Esta categoría incluye todos los espacios de nombres con los mismos dos primeros nodos de espacio de nombres `(<Company>.<Technology>*`), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="dca68-143">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="dca68-144">Es importante que los tipos que pertenecen a una sola tecnología no entren en conflicto entre sí.</span><span class="sxs-lookup"><span data-stu-id="dca68-144">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="dca68-145">❌ no asignar nombres de tipo que entren en conflicto con otros tipos dentro de una sola tecnología.</span><span class="sxs-lookup"><span data-stu-id="dca68-145">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="dca68-146">❌ no presentan conflictos de nombres de tipo entre los tipos de los espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no esté pensada para usarse con el modelo de aplicación).</span><span class="sxs-lookup"><span data-stu-id="dca68-146">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="dca68-147">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="dca68-147">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="dca68-148">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="dca68-148">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="dca68-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="dca68-149">See also</span></span>

- [<span data-ttu-id="dca68-150">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dca68-150">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="dca68-151">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="dca68-151">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
