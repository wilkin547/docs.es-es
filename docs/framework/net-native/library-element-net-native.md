---
title: Elemento &lt;Library&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2663bbd5ca93341455b7bd036469d25d91f4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="5718d-102">Elemento &lt;Library&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="5718d-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="5718d-103">Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5718d-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="5718d-104">Elemento \<Directives></span><span class="sxs-lookup"><span data-stu-id="5718d-104">\<Directives> Element</span></span>  
<span data-ttu-id="5718d-105">Elemento \<Library></span><span class="sxs-lookup"><span data-stu-id="5718d-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5718d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5718d-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5718d-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5718d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5718d-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5718d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5718d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5718d-109">Attributes</span></span>  
  
|<span data-ttu-id="5718d-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="5718d-110">Attribute</span></span>|<span data-ttu-id="5718d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5718d-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="5718d-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5718d-112">Required attribute.</span></span> <span data-ttu-id="5718d-113">Especifica el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5718d-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="5718d-114">Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5718d-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="5718d-115">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="5718d-115">Name attribute</span></span>  
  
|<span data-ttu-id="5718d-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5718d-116">Value</span></span>|<span data-ttu-id="5718d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5718d-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5718d-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="5718d-118">*assembly_name*</span></span>|<span data-ttu-id="5718d-119">Nombre simple del ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="5718d-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="5718d-120">Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5718d-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5718d-121">Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".</span><span class="sxs-lookup"><span data-stu-id="5718d-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="5718d-122">Vea la sección Comentarios para conocer una forma especial de *assembly_name* que admite la inclusión condicional de metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5718d-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5718d-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5718d-123">Child Elements</span></span>  
  
|<span data-ttu-id="5718d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5718d-124">Element</span></span>|<span data-ttu-id="5718d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5718d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5718d-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="5718d-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="5718d-127">Aplica la directiva a todos los tipos en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="5718d-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="5718d-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="5718d-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="5718d-129">Aplica la directiva a todos los tipos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="5718d-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="5718d-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="5718d-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="5718d-131">Aplica la directiva a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="5718d-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="5718d-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="5718d-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="5718d-133">Aplica la directiva a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="5718d-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="5718d-134">Por ejemplo, se podría usar un elemento [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) para definir la directiva para un tipo `List<String>`.</span><span class="sxs-lookup"><span data-stu-id="5718d-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5718d-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5718d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5718d-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="5718d-136">Element</span></span>|<span data-ttu-id="5718d-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="5718d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5718d-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="5718d-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="5718d-139">Elemento raíz de un archivo de directivas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5718d-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5718d-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5718d-140">Remarks</span></span>  
 <span data-ttu-id="5718d-141">El elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) puede contener cero, uno o más elementos `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="5718d-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="5718d-142">El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva.</span><span class="sxs-lookup"><span data-stu-id="5718d-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="5718d-143">En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5718d-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="5718d-144">Por el contrario, las herramientas del compilador buscan en todas las bibliotecas (incluidas las bibliotecas principales de .NET Framework), para encontrar los elementos de programa identificados por los elementos secundarios del elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="5718d-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="5718d-145">Las directivas de `<Library>` se pueden usar de manera condicional.</span><span class="sxs-lookup"><span data-stu-id="5718d-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="5718d-146">Si el nombre del elemento `<Library>` empieza y termina con un asterisco (*), la directiva `<Library>` tendrá efecto solo si la aplicación hace referencia al ensamblado especificado entre los asteriscos.</span><span class="sxs-lookup"><span data-stu-id="5718d-146">If the name of the `<Library>` element starts and ends with an asterisk (*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="5718d-147">Por ejemplo, la siguiente directiva en tiempo de ejecución se aplica únicamente si la aplicación hace referencia al ensamblado Utillities.dll.</span><span class="sxs-lookup"><span data-stu-id="5718d-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5718d-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5718d-148">See Also</span></span>  
 [<span data-ttu-id="5718d-149">\<Aplicación > elemento</span><span class="sxs-lookup"><span data-stu-id="5718d-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 [<span data-ttu-id="5718d-150">\<Directivas > elemento</span><span class="sxs-lookup"><span data-stu-id="5718d-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 [<span data-ttu-id="5718d-151">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="5718d-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="5718d-152">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="5718d-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
