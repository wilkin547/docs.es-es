---
title: Nombres de espacios de nombres
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bc298ad41884bfda84771a729990ebb4e6f776b7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-namespaces"></a><span data-ttu-id="2260a-102">Nombres de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="2260a-102">Names of Namespaces</span></span>
<span data-ttu-id="2260a-103">Como con otras directrices de nomenclaturas, el objetivo al asignar nombres a los espacios de nombres está creando una mayor claridad suficiente para los programadores que utilizan el marco de trabajo saber inmediatamente lo que es probable que el contenido del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="2260a-104">La plantilla siguiente especifica la regla general para asignar nombres a los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="2260a-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="2260a-105">Éstos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2260a-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="2260a-106">**✓ HACER** prefijos de espacios de nombres con un nombre de compañía para evitar que los espacios de nombres de distintas compañías que tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2260a-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="2260a-107">**✓ HACER** utilizar un nombre de producto estable, independiente de la versión en el segundo nivel de un nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="2260a-108">**X DO NOT** usar jerarquías organizativas como base para los nombres en las jerarquías de espacio de nombres, porque los nombres de grupo dentro de las organizaciones tienden a ser de corta duración.</span><span class="sxs-lookup"><span data-stu-id="2260a-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="2260a-109">Organizar la jerarquía de espacios de nombres alrededor de grupos de tecnologías relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2260a-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="2260a-110">**✓ HACER** usar Pascal y componentes del espacio de nombres independiente con puntos (por ejemplo, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="2260a-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="2260a-111">Si su marca utiliza una grafía no tradicional, debe seguir las mayúsculas y minúsculas definida por su marca, incluso si se desvían de mayúsculas y minúsculas del espacio de nombres normal.</span><span class="sxs-lookup"><span data-stu-id="2260a-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="2260a-112">**Considere la posibilidad de ✓** recurriendo plural espacios de nombres en su caso.</span><span class="sxs-lookup"><span data-stu-id="2260a-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="2260a-113">Por ejemplo, utilice `System.Collections` en lugar de `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="2260a-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="2260a-114">Nombres de marcas y acrónimos son excepciones a esta regla, sin embargo.</span><span class="sxs-lookup"><span data-stu-id="2260a-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="2260a-115">Por ejemplo, utilice `System.IO` en lugar de `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="2260a-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="2260a-116">**X DO NOT** usar el mismo nombre para un espacio de nombres y un tipo en ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="2260a-117">Por ejemplo, no use `Debug` como un espacio de nombres nombre y, a continuación, proporcionar también una clase denominada `Debug` en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="2260a-118">Algunos compiladores requieren estos tipos estén completos.</span><span class="sxs-lookup"><span data-stu-id="2260a-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="2260a-119">Espacios de nombres y conflictos de nombres de tipo</span><span class="sxs-lookup"><span data-stu-id="2260a-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="2260a-120">**X DO NOT** introducir los nombres de tipos genéricos como `Element`, `Node`, `Log`, y `Message`.</span><span class="sxs-lookup"><span data-stu-id="2260a-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="2260a-121">Hay una probabilidad muy alta de que si se hace, dará lugar a escriba nombre entra en conflicto en común escenarios.</span><span class="sxs-lookup"><span data-stu-id="2260a-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="2260a-122">Debe calificar los nombres de tipo genérico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="2260a-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="2260a-123">Hay instrucciones específicas para evitar conflictos de nombre de tipo para las diferentes categorías de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="2260a-124">**Espacios de nombres del modelo de aplicación**</span><span class="sxs-lookup"><span data-stu-id="2260a-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="2260a-125">Espacios de nombres que pertenecen a un único modelo de aplicación muy a menudo se usan juntos, pero casi nunca se usan con los espacios de nombres de otros modelos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2260a-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="2260a-126">Por ejemplo, el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres con poca frecuencia se utiliza junto con el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2260a-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="2260a-127">La siguiente es una lista de grupos de espacio de nombres del modelo de aplicación conocida:</span><span class="sxs-lookup"><span data-stu-id="2260a-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="2260a-128">**X DO NOT** dar el mismo nombre a los tipos de espacios de nombres dentro de un único modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2260a-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="2260a-129">Por ejemplo, no agregue un tipo denominado `Page` a la <xref:System.Web.UI.Adapters?displayProperty=nameWithType> espacio de nombres, porque el <xref:System.Web.UI?displayProperty=nameWithType> espacio de nombres ya contiene un tipo denominado `Page`.</span><span class="sxs-lookup"><span data-stu-id="2260a-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="2260a-130">**Espacios de nombres de infraestructura**</span><span class="sxs-lookup"><span data-stu-id="2260a-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="2260a-131">Este grupo contiene los espacios de nombres que rara vez se hayan importado durante el desarrollo de aplicaciones comunes.</span><span class="sxs-lookup"><span data-stu-id="2260a-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="2260a-132">Por ejemplo, `.Design` los espacios de nombres se usan principalmente al desarrollar la programación de las herramientas.</span><span class="sxs-lookup"><span data-stu-id="2260a-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="2260a-133">Evitar conflictos con los tipos de estos espacios de nombres no es crítico.</span><span class="sxs-lookup"><span data-stu-id="2260a-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="2260a-134">**Espacios de nombres básicos**</span><span class="sxs-lookup"><span data-stu-id="2260a-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="2260a-135">Espacios de nombres básicos incluyen todas `System` espacios de nombres, excluyendo los espacios de nombres de los modelos de aplicación y los espacios de nombres de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="2260a-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="2260a-136">Espacios de nombres básicos se incluyen, entre otros, `System`, `System.IO`, `System.Xml`, y `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="2260a-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="2260a-137">**X DO NOT** ofrecen a tipos de nombres que entrarían en conflicto con ningún tipo en los espacios de nombres principal.</span><span class="sxs-lookup"><span data-stu-id="2260a-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="2260a-138">Por ejemplo, nunca use `Stream` como nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="2260a-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="2260a-139">Entraría en conflicto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo muy frecuente.</span><span class="sxs-lookup"><span data-stu-id="2260a-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="2260a-140">**Grupos de espacio de nombres de tecnología**</span><span class="sxs-lookup"><span data-stu-id="2260a-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="2260a-141">Esta categoría incluye todos los espacios de nombres con los dos primeros nodos de espacio de nombres mismo `(<Company>.<Technology>*`), como `Microsoft.Build.Utilities` y `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="2260a-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="2260a-142">Es importante que los tipos que pertenecen a una sola tecnología no entren en conflicto entre sí.</span><span class="sxs-lookup"><span data-stu-id="2260a-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="2260a-143">**X DO NOT** asignar nombres de tipos que entrarían en conflicto con otros tipos de una sola tecnología.</span><span class="sxs-lookup"><span data-stu-id="2260a-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="2260a-144">**X DO NOT** presentan conflictos de nombre de tipo entre los tipos de espacios de nombres de tecnología y un espacio de nombres del modelo de aplicación (a menos que la tecnología no está diseñada para utilizarse con el modelo de aplicación).</span><span class="sxs-lookup"><span data-stu-id="2260a-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="2260a-145">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="2260a-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2260a-146">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2260a-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2260a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="2260a-147">See Also</span></span>  
 [<span data-ttu-id="2260a-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2260a-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="2260a-149">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="2260a-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
