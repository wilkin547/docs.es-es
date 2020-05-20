---
title: Nombres de espacios de nombres
description: Siga estas instrucciones para asignar nombres a los espacios de nombres como parte de las instrucciones para diseñar bibliotecas que extienden e interactúan con las bibliotecas de .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 0ad98af240cf8d1041d6a8b64ab71a56e763f76f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419062"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="90f67-103">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="90f67-103">Names of Namespaces</span></span>
<span data-ttu-id="90f67-104">Como ocurre con otras directrices de nomenclatura, el objetivo de asignar nombres a los espacios de nombres es crear una claridad suficiente para que el programador use el marco de trabajo para saber inmediatamente cuál es el contenido del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-104">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="90f67-105">La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="90f67-105">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="90f67-106">A continuación, se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="90f67-106">The following are examples:</span></span>

 <span data-ttu-id="90f67-107">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="90f67-107">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="90f67-108">✔️ prefijar los nombres de los espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas empresas tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="90f67-108">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="90f67-109">✔️ usar un nombre de producto estable y independiente de la versión en el segundo nivel de un nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-109">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="90f67-110">❌No utilice jerarquías organizativas como base para los nombres de las jerarquías de espacio de nombres, ya que los nombres de grupo dentro de las organizaciones tienden a ser de corta duración.</span><span class="sxs-lookup"><span data-stu-id="90f67-110">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="90f67-111">Organice la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.</span><span class="sxs-lookup"><span data-stu-id="90f67-111">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="90f67-112">✔️ usar PascalCasing y separar los componentes de los espacios de nombres con puntos (por ejemplo, `Microsoft.Office.PowerPoint` ).</span><span class="sxs-lookup"><span data-stu-id="90f67-112">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="90f67-113">Si la marca emplea una grafía no tradicional, debe seguir las mayúsculas y minúsculas definidas por la marca, incluso si se desvía de la grafía normal del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-113">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="90f67-114">✔️ CONSIDERE el uso de nombres de espacios de nombres plurales cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="90f67-114">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="90f67-115">Por ejemplo, use `System.Collections` en lugar de `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="90f67-115">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="90f67-116">Sin embargo, los nombres de marca y los acrónimos son excepciones a esta regla.</span><span class="sxs-lookup"><span data-stu-id="90f67-116">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="90f67-117">Por ejemplo, use `System.IO` en lugar de `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="90f67-117">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="90f67-118">❌No use el mismo nombre para un espacio de nombres y un tipo en dicho espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-118">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="90f67-119">Por ejemplo, no use `Debug` como nombre de espacio de nombres y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-119">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="90f67-120">Varios compiladores requieren que estos tipos sean completos.</span><span class="sxs-lookup"><span data-stu-id="90f67-120">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="90f67-121">Conflictos de nombres de tipos y espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="90f67-121">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="90f67-122">❌No introduzca nombres de tipo genéricos como `Element` , `Node` , `Log` y `Message` .</span><span class="sxs-lookup"><span data-stu-id="90f67-122">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="90f67-123">Existe una probabilidad muy alta de que esto provocará conflictos de nombres de tipo en escenarios comunes.</span><span class="sxs-lookup"><span data-stu-id="90f67-123">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="90f67-124">Debe calificar los nombres de tipos genéricos ( `FormElement` , `XmlNode` , `EventLog` , `SoapMessage` ).</span><span class="sxs-lookup"><span data-stu-id="90f67-124">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="90f67-125">Existen directrices específicas para evitar conflictos de nombres de tipo para distintas categorías de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-125">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="90f67-126">**Espacios de nombres del modelo de aplicación**</span><span class="sxs-lookup"><span data-stu-id="90f67-126">**Application model namespaces**</span></span>

     <span data-ttu-id="90f67-127">Los espacios de nombres que pertenecen a un único modelo de aplicación suelen usarse juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="90f67-127">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="90f67-128">Por ejemplo, el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres se suele usar junto con el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="90f67-128">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="90f67-129">A continuación se muestra una lista de grupos de espacios de nombres del modelo de aplicación conocidos:</span><span class="sxs-lookup"><span data-stu-id="90f67-129">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="90f67-130">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="90f67-130">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="90f67-131">❌NO asigne el mismo nombre a los tipos de los espacios de nombres dentro de un único modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="90f67-131">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="90f67-132">Por ejemplo, no agregue un tipo denominado `Page` al espacio de <xref:System.Web.UI.Adapters?displayProperty=nameWithType> nombres, ya que el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres ya contiene un tipo denominado `Page` .</span><span class="sxs-lookup"><span data-stu-id="90f67-132">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="90f67-133">**Espacios de nombres de infraestructura**</span><span class="sxs-lookup"><span data-stu-id="90f67-133">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="90f67-134">Este grupo contiene espacios de nombres que rara vez se importan durante el desarrollo de aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="90f67-134">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="90f67-135">Por ejemplo, los `.Design` espacios de nombres se utilizan principalmente al desarrollar herramientas de programación.</span><span class="sxs-lookup"><span data-stu-id="90f67-135">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="90f67-136">Evitar conflictos con tipos en estos espacios de nombres no es crítico.</span><span class="sxs-lookup"><span data-stu-id="90f67-136">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="90f67-137">**Espacios de nombres principales**</span><span class="sxs-lookup"><span data-stu-id="90f67-137">**Core namespaces**</span></span>

     <span data-ttu-id="90f67-138">Los espacios de nombres principales incluyen todos los `System` espacios de nombres, excluidos los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="90f67-138">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="90f67-139">Los espacios de nombres principales incluyen, entre otros, `System` ,, `System.IO` `System.Xml` y `System.Net` .</span><span class="sxs-lookup"><span data-stu-id="90f67-139">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="90f67-140">❌NO proporcione nombres de tipos que entren en conflicto con cualquier tipo de los espacios de nombres principales.</span><span class="sxs-lookup"><span data-stu-id="90f67-140">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="90f67-141">Por ejemplo, nunca use `Stream` como nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="90f67-141">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="90f67-142">Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType> , un tipo de uso muy común.</span><span class="sxs-lookup"><span data-stu-id="90f67-142">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="90f67-143">**Grupos de espacios de nombres de tecnología**</span><span class="sxs-lookup"><span data-stu-id="90f67-143">**Technology namespace groups**</span></span>

     <span data-ttu-id="90f67-144">Esta categoría incluye todos los espacios de nombres con los mismos dos primeros nodos de espacio `(<Company>.<Technology>*` de nombres), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks` .</span><span class="sxs-lookup"><span data-stu-id="90f67-144">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="90f67-145">Es importante que los tipos que pertenecen a una sola tecnología no entren en conflicto entre sí.</span><span class="sxs-lookup"><span data-stu-id="90f67-145">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="90f67-146">❌NO asigne nombres de tipo que entren en conflicto con otros tipos dentro de una sola tecnología.</span><span class="sxs-lookup"><span data-stu-id="90f67-146">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="90f67-147">❌No introduzca conflictos de nombres de tipo entre los tipos de los espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no esté pensada para usarse con el modelo de aplicación).</span><span class="sxs-lookup"><span data-stu-id="90f67-147">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="90f67-148">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="90f67-148">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="90f67-149">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="90f67-149">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="90f67-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="90f67-150">See also</span></span>

- [<span data-ttu-id="90f67-151">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="90f67-151">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="90f67-152">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="90f67-152">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
