---
title: Elemento &lt;Library&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6615ab30fdc0d0ab65f135e1df4e206f5548dc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743795"
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="5b808-102">Elemento &lt;Library&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="5b808-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="5b808-103">Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b808-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="5b808-104">Elemento \<Directives></span><span class="sxs-lookup"><span data-stu-id="5b808-104">\<Directives> Element</span></span>  
<span data-ttu-id="5b808-105">Elemento \<Library></span><span class="sxs-lookup"><span data-stu-id="5b808-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b808-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b808-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b808-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b808-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5b808-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b808-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b808-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b808-109">Attributes</span></span>  
  
|<span data-ttu-id="5b808-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b808-110">Attribute</span></span>|<span data-ttu-id="5b808-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b808-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="5b808-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5b808-112">Required attribute.</span></span> <span data-ttu-id="5b808-113">Especifica el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b808-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="5b808-114">Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b808-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="5b808-115">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="5b808-115">Name attribute</span></span>  
  
|<span data-ttu-id="5b808-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5b808-116">Value</span></span>|<span data-ttu-id="5b808-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b808-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b808-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="5b808-118">*assembly_name*</span></span>|<span data-ttu-id="5b808-119">Nombre simple del ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="5b808-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="5b808-120">Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b808-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="5b808-121">Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".</span><span class="sxs-lookup"><span data-stu-id="5b808-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="5b808-122">Vea la sección Comentarios para conocer una forma especial de *assembly_name* que admite la inclusión condicional de metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b808-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b808-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b808-123">Child Elements</span></span>  
  
|<span data-ttu-id="5b808-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b808-124">Element</span></span>|<span data-ttu-id="5b808-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b808-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b808-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="5b808-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="5b808-127">Aplica la directiva a todos los tipos en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="5b808-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="5b808-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="5b808-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="5b808-129">Aplica la directiva a todos los tipos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="5b808-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="5b808-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="5b808-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="5b808-131">Aplica la directiva a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="5b808-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="5b808-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="5b808-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="5b808-133">Aplica la directiva a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="5b808-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="5b808-134">Por ejemplo, se podría usar un elemento [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) para definir la directiva para un tipo `List<String>`.</span><span class="sxs-lookup"><span data-stu-id="5b808-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b808-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b808-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5b808-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b808-136">Element</span></span>|<span data-ttu-id="5b808-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b808-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b808-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="5b808-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="5b808-139">Elemento raíz de un archivo de directivas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5b808-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b808-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b808-140">Remarks</span></span>  
 <span data-ttu-id="5b808-141">El elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) puede contener cero, uno o más elementos `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="5b808-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="5b808-142">El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva.</span><span class="sxs-lookup"><span data-stu-id="5b808-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="5b808-143">En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5b808-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="5b808-144">Por el contrario, las herramientas del compilador buscan en todas las bibliotecas (incluidas las bibliotecas principales de .NET Framework), para encontrar los elementos de programa identificados por los elementos secundarios del elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="5b808-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="5b808-145">Las directivas de `<Library>` se pueden usar de manera condicional.</span><span class="sxs-lookup"><span data-stu-id="5b808-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="5b808-146">Si el nombre de la `<Library>` elemento comienza y termina con un asterisco (\*), el `<Library>` directiva tiene un efecto sólo si se hace referencia el ensamblado especificado entre los asteriscos por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b808-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="5b808-147">Por ejemplo, la siguiente directiva en tiempo de ejecución se aplica únicamente si la aplicación hace referencia al ensamblado Utillities.dll.</span><span class="sxs-lookup"><span data-stu-id="5b808-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b808-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b808-148">See also</span></span>
- [<span data-ttu-id="5b808-149">\<Aplicación > elemento</span><span class="sxs-lookup"><span data-stu-id="5b808-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)
- [<span data-ttu-id="5b808-150">\<Directivas > elemento</span><span class="sxs-lookup"><span data-stu-id="5b808-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)
- [<span data-ttu-id="5b808-151">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="5b808-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="5b808-152">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="5b808-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
