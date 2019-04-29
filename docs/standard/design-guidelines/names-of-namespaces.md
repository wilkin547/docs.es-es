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
author: KrzysztofCwalina
ms.openlocfilehash: 0099c5c8a863023099b377e139461606de3e1e1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940990"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="5cd5c-102">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="5cd5c-102">Names of Namespaces</span></span>
<span data-ttu-id="5cd5c-103">Como con otras directrices de nomenclatura, el objetivo al asignar nombres a los espacios de nombres está creando una mayor claridad suficiente para los programadores que utilizan el marco de trabajo saber inmediatamente lo que es probable que sea el contenido del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="5cd5c-104">La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="5cd5c-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="5cd5c-105">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5cd5c-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="5cd5c-106">**✓ DO** prefijos de espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas compañías que tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="5cd5c-107">**✓ DO** utilizar un nombre de producto estable, independiente de la versión en el segundo nivel de un nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="5cd5c-108">**X DO NOT** usar jerarquías organizativas como base para los nombres en las jerarquías de espacio de nombres, porque los nombres de grupo dentro de las organizaciones tienden a ser de corta duración.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="5cd5c-109">Organizar la jerarquía de espacios de nombres en torno a grupos de tecnologías relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="5cd5c-110">**✓ DO** usar Pascal y componentes del espacio de nombres independiente con puntos (por ejemplo, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="5cd5c-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="5cd5c-111">Si su marca utiliza una grafía no tradicional, debe seguir las mayúsculas y minúsculas definida por su marca, incluso si se desvían de espacio de nombres normal de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="5cd5c-112">**✓ CONSIDER** recurriendo plural espacios de nombres en su caso.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="5cd5c-113">Por ejemplo, use `System.Collections` en lugar de `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="5cd5c-114">Nombres y acrónimos son excepciones a esta regla, sin embargo.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="5cd5c-115">Por ejemplo, use `System.IO` en lugar de `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="5cd5c-116">**X DO NOT** usar el mismo nombre para un espacio de nombres y un tipo en ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="5cd5c-117">Por ejemplo, no use `Debug` como un espacio de nombres que asigne un nombre y, a continuación, proporcione también una clase denominada `Debug` en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="5cd5c-118">Algunos compiladores requieren ser un nombre completo de dichos tipos.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="5cd5c-119">Espacios de nombres y los conflictos de nombre de tipo</span><span class="sxs-lookup"><span data-stu-id="5cd5c-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="5cd5c-120">**X DO NOT** introducir los nombres de tipos genéricos como `Element`, `Node`, `Log`, y `Message`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="5cd5c-121">Hay una probabilidad muy alta de que al hacerlo, por lo que dará lugar a que se escriba el nombre entra en conflicto en común los escenarios.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="5cd5c-122">Se deben calificar los nombres de tipo genérico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="5cd5c-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="5cd5c-123">Hay instrucciones específicas para evitar conflictos de nombre de tipo para las diferentes categorías de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="5cd5c-124">**Espacios de nombres del modelo de aplicación**</span><span class="sxs-lookup"><span data-stu-id="5cd5c-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="5cd5c-125">Los espacios de nombres que pertenecen a un único modelo de aplicación muy a menudo se usan juntos, pero casi nunca se usan con espacios de nombres de otros modelos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="5cd5c-126">Por ejemplo, el <xref:System.Windows.Forms?displayProperty=nameWithType> muy rara vez se utiliza el espacio de nombres junto con el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5cd5c-127">La siguiente es una lista de grupos de espacio de nombres del modelo de aplicación conocida:</span><span class="sxs-lookup"><span data-stu-id="5cd5c-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="5cd5c-128">**X DO NOT** dar el mismo nombre a los tipos de espacios de nombres dentro de un único modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="5cd5c-129">Por ejemplo, no agregue un tipo denominado `Page` a la <xref:System.Web.UI.Adapters?displayProperty=nameWithType> espacio de nombres, porque el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres ya contiene un tipo denominado `Page`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="5cd5c-130">**Espacios de nombres de la infraestructura**</span><span class="sxs-lookup"><span data-stu-id="5cd5c-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="5cd5c-131">Este grupo contiene los espacios de nombres que se importan rara vez durante el desarrollo de aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="5cd5c-132">Por ejemplo, `.Design` espacios de nombres se utilizan principalmente al desarrollo de programación de las herramientas.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="5cd5c-133">Evitar conflictos con los tipos de estos espacios de nombres no es fundamental.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="5cd5c-134">**Espacios de nombres básicos**</span><span class="sxs-lookup"><span data-stu-id="5cd5c-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="5cd5c-135">Espacios de nombres básicos incluyen todos `System` espacios de nombres, excepto los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="5cd5c-136">Espacios de nombres básicos se incluyen, entre otros, `System`, `System.IO`, `System.Xml`, y `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="5cd5c-137">**X DO NOT** ofrecen a tipos de nombres que entrarían en conflicto con ningún tipo en los espacios de nombres principal.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="5cd5c-138">Por ejemplo, nunca use `Stream` como un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="5cd5c-139">Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo muy frecuente.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="5cd5c-140">**Grupos de espacio de nombres de tecnología**</span><span class="sxs-lookup"><span data-stu-id="5cd5c-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="5cd5c-141">Esta categoría incluye todos los espacios de nombres con los dos primeros nodos de espacio de nombres mismo `(<Company>.<Technology>*`), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="5cd5c-142">Es importante que los tipos que pertenecen a una única tecnología no entran en conflicto entre sí.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="5cd5c-143">**X DO NOT** asignar nombres de tipos que entrarían en conflicto con otros tipos de una sola tecnología.</span><span class="sxs-lookup"><span data-stu-id="5cd5c-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="5cd5c-144">**X DO NOT** presentan conflictos de nombre de tipo entre los tipos de espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no está diseñada para utilizarse con el modelo de aplicación).</span><span class="sxs-lookup"><span data-stu-id="5cd5c-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="5cd5c-145">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="5cd5c-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5cd5c-146">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5cd5c-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd5c-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd5c-147">See also</span></span>

- [<span data-ttu-id="5cd5c-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5cd5c-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="5cd5c-149">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="5cd5c-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
