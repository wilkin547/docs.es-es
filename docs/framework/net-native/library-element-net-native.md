---
description: 'Más información sobre: <Library> elemento (.net Native)'
title: <Library> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: 224b2b9cbce8123f4a15b9ec3e3793674633822a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747613"
---
# <a name="library-element-net-native"></a><span data-ttu-id="95d14-103">\<Library> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="95d14-103">\<Library> Element (.NET Native)</span></span>

<span data-ttu-id="95d14-104">Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="95d14-104">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="95d14-105">\<Directives> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="95d14-105">\<Directives> Element</span></span>  
<span data-ttu-id="95d14-106">\<Library> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="95d14-106">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95d14-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95d14-107">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95d14-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95d14-108">Attributes and Elements</span></span>  

 <span data-ttu-id="95d14-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95d14-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95d14-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="95d14-110">Attributes</span></span>  
  
|<span data-ttu-id="95d14-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="95d14-111">Attribute</span></span>|<span data-ttu-id="95d14-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="95d14-112">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="95d14-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="95d14-113">Required attribute.</span></span> <span data-ttu-id="95d14-114">Especifica el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95d14-114">Specifies the name of an assembly.</span></span> <span data-ttu-id="95d14-115">Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95d14-115">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="95d14-116">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="95d14-116">Name attribute</span></span>  
  
|<span data-ttu-id="95d14-117">Value</span><span class="sxs-lookup"><span data-stu-id="95d14-117">Value</span></span>|<span data-ttu-id="95d14-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="95d14-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95d14-119">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="95d14-119">*assembly_name*</span></span>|<span data-ttu-id="95d14-120">Nombre simple del ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="95d14-120">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="95d14-121">Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="95d14-121">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="95d14-122">Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".</span><span class="sxs-lookup"><span data-stu-id="95d14-122">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="95d14-123">Vea la sección Comentarios para conocer una forma especial de *assembly_name* que admite la inclusión condicional de metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95d14-123">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95d14-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95d14-124">Child Elements</span></span>  
  
|<span data-ttu-id="95d14-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="95d14-125">Element</span></span>|<span data-ttu-id="95d14-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="95d14-126">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="95d14-127">Aplica la directiva a todos los tipos en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="95d14-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="95d14-128">Aplica la directiva a todos los tipos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="95d14-128">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="95d14-129">Aplica la directiva a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="95d14-129">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="95d14-130">Aplica la directiva a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="95d14-130">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="95d14-131">Por ejemplo, un [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elemento podría usarse para definir la Directiva para un `List<String>` tipo.</span><span class="sxs-lookup"><span data-stu-id="95d14-131">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95d14-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95d14-132">Parent Elements</span></span>  
  
|<span data-ttu-id="95d14-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="95d14-133">Element</span></span>|<span data-ttu-id="95d14-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="95d14-134">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="95d14-135">Elemento raíz de un archivo de directivas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="95d14-135">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95d14-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="95d14-136">Remarks</span></span>  

 <span data-ttu-id="95d14-137">El [\<Directives>](directives-element-net-native.md) elemento puede contener cero, uno o más `<Library>` elementos.</span><span class="sxs-lookup"><span data-stu-id="95d14-137">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="95d14-138">El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva.</span><span class="sxs-lookup"><span data-stu-id="95d14-138">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="95d14-139">En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="95d14-139">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="95d14-140">En cambio, las herramientas de compilador buscan en todas las bibliotecas, including.NET Framework Core Libraries, los elementos de programa identificados por los elementos secundarios del [\<Application>](application-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="95d14-140">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="95d14-141">Las directivas de `<Library>` se pueden usar de manera condicional.</span><span class="sxs-lookup"><span data-stu-id="95d14-141">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="95d14-142">Si el nombre del `<Library>` elemento comienza y termina con un asterisco ( \* ), la `<Library>` directiva solo tiene efecto si la aplicación hace referencia al ensamblado especificado entre los asteriscos.</span><span class="sxs-lookup"><span data-stu-id="95d14-142">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="95d14-143">Por ejemplo, la siguiente directiva en tiempo de ejecución solo se aplica si la aplicación hace referencia al ensamblado Utilities.dll.</span><span class="sxs-lookup"><span data-stu-id="95d14-143">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95d14-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="95d14-144">See also</span></span>

- [<span data-ttu-id="95d14-145">Elemento \<Application></span><span class="sxs-lookup"><span data-stu-id="95d14-145">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="95d14-146">Elemento \<Directives></span><span class="sxs-lookup"><span data-stu-id="95d14-146">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="95d14-147">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="95d14-147">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="95d14-148">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="95d14-148">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
