---
title: <Library>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: f94bfe047fa7a95b6f24264bae0b27112c589dfd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128363"
---
# <a name="library-element-net-native"></a><span data-ttu-id="b7847-102">\<Library>Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b7847-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="b7847-103">Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7847-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="b7847-104">\<Directives> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="b7847-104">\<Directives> Element</span></span>  
<span data-ttu-id="b7847-105">\<Library> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="b7847-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7847-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7847-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7847-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7847-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b7847-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b7847-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7847-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7847-109">Attributes</span></span>  
  
|<span data-ttu-id="b7847-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="b7847-110">Attribute</span></span>|<span data-ttu-id="b7847-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7847-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="b7847-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b7847-112">Required attribute.</span></span> <span data-ttu-id="b7847-113">Especifica el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b7847-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="b7847-114">Los elementos secundarios de este elemento `<Library>` definen la directiva de reflexión en tiempo de ejecución para los tipos y miembros de tipos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b7847-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b7847-115">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="b7847-115">Name attribute</span></span>  
  
|<span data-ttu-id="b7847-116">Value</span><span class="sxs-lookup"><span data-stu-id="b7847-116">Value</span></span>|<span data-ttu-id="b7847-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7847-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7847-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="b7847-118">*assembly_name*</span></span>|<span data-ttu-id="b7847-119">Nombre simple del ensamblado sin la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="b7847-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="b7847-120">Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7847-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="b7847-121">Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".</span><span class="sxs-lookup"><span data-stu-id="b7847-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="b7847-122">Vea la sección Comentarios para conocer una forma especial de *assembly_name* que admite la inclusión condicional de metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b7847-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7847-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7847-123">Child Elements</span></span>  
  
|<span data-ttu-id="b7847-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7847-124">Element</span></span>|<span data-ttu-id="b7847-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7847-125">Description</span></span>|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|<span data-ttu-id="b7847-126">Aplica la directiva a todos los tipos en un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="b7847-126">Applies policy to all the types in a particular assembly.</span></span>|  
|[\<Namespace>](namespace-element-net-native.md)|<span data-ttu-id="b7847-127">Aplica la directiva a todos los tipos en un espacio de nombres determinado.</span><span class="sxs-lookup"><span data-stu-id="b7847-127">Applies policy to all the types in a particular namespace.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="b7847-128">Aplica la directiva a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="b7847-128">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="b7847-129">Aplica la directiva a un tipo genérico construido.</span><span class="sxs-lookup"><span data-stu-id="b7847-129">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="b7847-130">Por ejemplo, un [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elemento podría usarse para definir la Directiva para un `List<String>` tipo.</span><span class="sxs-lookup"><span data-stu-id="b7847-130">For example, a [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7847-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7847-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b7847-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7847-132">Element</span></span>|<span data-ttu-id="b7847-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7847-133">Description</span></span>|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|<span data-ttu-id="b7847-134">Elemento raíz de un archivo de directivas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7847-134">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7847-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7847-135">Remarks</span></span>  
 <span data-ttu-id="b7847-136">El [\<Directives>](directives-element-net-native.md) elemento puede contener cero, uno o más `<Library>` elementos.</span><span class="sxs-lookup"><span data-stu-id="b7847-136">The [\<Directives>](directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="b7847-137">El elemento `<Library>` sirve de contenedor para definir los elementos de programa cuyos metadatos son necesarios en tiempo de ejecución. Este elemento no expresa la directiva.</span><span class="sxs-lookup"><span data-stu-id="b7847-137">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="b7847-138">En tiempo de compilación, las herramientas del compilador buscan únicamente en la biblioteca designada por el elemento `<Library>` para encontrar los elementos de programa identificados por sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b7847-138">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="b7847-139">En cambio, las herramientas de compilador buscan en todas las bibliotecas, including.NET Framework Core Libraries, los elementos de programa identificados por los elementos secundarios del [\<Application>](application-element-net-native.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b7847-139">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="b7847-140">Las directivas de `<Library>` se pueden usar de manera condicional.</span><span class="sxs-lookup"><span data-stu-id="b7847-140">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="b7847-141">Si el nombre del `<Library>` elemento comienza y termina con un asterisco ( \* ), la `<Library>` directiva solo tiene efecto si la aplicación hace referencia al ensamblado especificado entre los asteriscos.</span><span class="sxs-lookup"><span data-stu-id="b7847-141">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="b7847-142">Por ejemplo, la siguiente directiva en tiempo de ejecución solo se aplica si la aplicación hace referencia al ensamblado Utilities. dll.</span><span class="sxs-lookup"><span data-stu-id="b7847-142">For example, the following runtime directive applies only if the Utilities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7847-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7847-143">See also</span></span>

- [<span data-ttu-id="b7847-144">\<Application>Element</span><span class="sxs-lookup"><span data-stu-id="b7847-144">\<Application> Element</span></span>](application-element-net-native.md)
- [<span data-ttu-id="b7847-145">\<Directives>Element</span><span class="sxs-lookup"><span data-stu-id="b7847-145">\<Directives> Element</span></span>](directives-element-net-native.md)
- [<span data-ttu-id="b7847-146">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="b7847-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b7847-147">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b7847-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
