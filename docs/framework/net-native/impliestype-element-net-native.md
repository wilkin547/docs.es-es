---
description: 'Más información sobre: <ImpliesType> elemento (.net Native)'
title: <ImpliesType> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 6476876f335788a276907fd2aef02d5623382699
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747691"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="68693-103">\<ImpliesType> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="68693-103">\<ImpliesType> Element (.NET Native)</span></span>

<span data-ttu-id="68693-104">Aplica una directiva a un tipo, si dicha directiva se ha aplicado al tipo contenedor o al método.</span><span class="sxs-lookup"><span data-stu-id="68693-104">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68693-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68693-105">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
             Browse="policy_type"  
             Dynamic="policy_type"  
             Serialize="policy_type"
             DataContractSerializer="policy_setting"  
             DataContractJsonSerializer="policy_setting"  
             XmlSerializer="policy_setting"  
             MarshalObject="policy_setting"  
             MarshalDelegate="policy_setting"  
             MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68693-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68693-106">Attributes and Elements</span></span>  

 <span data-ttu-id="68693-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68693-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68693-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="68693-108">Attributes</span></span>  
  
|<span data-ttu-id="68693-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="68693-109">Attribute</span></span>|<span data-ttu-id="68693-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="68693-110">Attribute type</span></span>|<span data-ttu-id="68693-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="68693-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="68693-112">General</span><span class="sxs-lookup"><span data-stu-id="68693-112">General</span></span>|<span data-ttu-id="68693-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="68693-113">Required attribute.</span></span> <span data-ttu-id="68693-114">Especifica el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="68693-114">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="68693-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="68693-115">Reflection</span></span>|<span data-ttu-id="68693-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-116">Optional attribute.</span></span> <span data-ttu-id="68693-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="68693-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="68693-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="68693-118">Reflection</span></span>|<span data-ttu-id="68693-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-119">Optional attribute.</span></span> <span data-ttu-id="68693-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="68693-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="68693-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="68693-121">Reflection</span></span>|<span data-ttu-id="68693-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-122">Optional attribute.</span></span> <span data-ttu-id="68693-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="68693-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="68693-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="68693-124">Serialization</span></span>|<span data-ttu-id="68693-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-125">Optional attribute.</span></span> <span data-ttu-id="68693-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="68693-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="68693-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="68693-127">Serialization</span></span>|<span data-ttu-id="68693-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-128">Optional attribute.</span></span> <span data-ttu-id="68693-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68693-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="68693-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="68693-130">Serialization</span></span>|<span data-ttu-id="68693-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-131">Optional attribute.</span></span> <span data-ttu-id="68693-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68693-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="68693-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="68693-133">Serialization</span></span>|<span data-ttu-id="68693-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-134">Optional attribute.</span></span> <span data-ttu-id="68693-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68693-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="68693-136">Interop</span><span class="sxs-lookup"><span data-stu-id="68693-136">Interop</span></span>|<span data-ttu-id="68693-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-137">Optional attribute.</span></span> <span data-ttu-id="68693-138">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="68693-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="68693-139">Interop</span><span class="sxs-lookup"><span data-stu-id="68693-139">Interop</span></span>|<span data-ttu-id="68693-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-140">Optional attribute.</span></span> <span data-ttu-id="68693-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="68693-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="68693-142">Interop</span><span class="sxs-lookup"><span data-stu-id="68693-142">Interop</span></span>|<span data-ttu-id="68693-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="68693-143">Optional attribute.</span></span> <span data-ttu-id="68693-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="68693-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="68693-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="68693-145">Name attribute</span></span>  
  
|<span data-ttu-id="68693-146">Value</span><span class="sxs-lookup"><span data-stu-id="68693-146">Value</span></span>|<span data-ttu-id="68693-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="68693-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68693-148">*type_name*</span><span class="sxs-lookup"><span data-stu-id="68693-148">*type_name*</span></span>|<span data-ttu-id="68693-149">Nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="68693-149">The type name.</span></span> <span data-ttu-id="68693-150">Si el tipo representado por este elemento `<ImpliesType>` se encuentra en el mismo espacio de nombres que su elemento contenedor `<Type>`, *type_name* puede incluir el nombre del tipo sin su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="68693-150">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="68693-151">De lo contrario, *type_name* debe incluir el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="68693-151">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="68693-152">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="68693-152">All other attributes</span></span>  
  
|<span data-ttu-id="68693-153">Value</span><span class="sxs-lookup"><span data-stu-id="68693-153">Value</span></span>|<span data-ttu-id="68693-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="68693-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68693-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="68693-155">*policy_setting*</span></span>|<span data-ttu-id="68693-156">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="68693-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="68693-157">Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="68693-157">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="68693-158">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="68693-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68693-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68693-159">Child Elements</span></span>  

 <span data-ttu-id="68693-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68693-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68693-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68693-161">Parent Elements</span></span>  
  
|<span data-ttu-id="68693-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="68693-162">Element</span></span>|<span data-ttu-id="68693-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="68693-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="68693-164">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="68693-164">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="68693-165">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="68693-165">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="68693-166">Aplica la directiva de reflexión a un método.</span><span class="sxs-lookup"><span data-stu-id="68693-166">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68693-167">Observaciones</span><span class="sxs-lookup"><span data-stu-id="68693-167">Remarks</span></span>  

 <span data-ttu-id="68693-168">El elemento `<ImpliesType>` sirve principalmente para que lo utilicen las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="68693-168">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="68693-169">Está pensado para el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="68693-169">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="68693-170">Si una rutina debe reflejarse en un determinado tipo, necesariamente debe reflejarse en un segundo tipo.</span><span class="sxs-lookup"><span data-stu-id="68693-170">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="68693-171">Los metadatos para la creación de instancias implícita del segundo tipo no está disponible, ya que el análisis estático no indica si es necesario.</span><span class="sxs-lookup"><span data-stu-id="68693-171">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="68693-172">Normalmente, los dos tipos son instancias genéricas con argumentos de tipo compartido.</span><span class="sxs-lookup"><span data-stu-id="68693-172">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="68693-173">El elemento `<ImpliesType>` se definió con la suposición de que una necesidad de reflexión en el tipo especificado por su elemento primario implica una necesidad de reflexión en el tipo especificado por el elemento `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="68693-173">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="68693-174">Por ejemplo, las siguientes directivas de reflexión se aplican en dos tipos, `Explicit<T>` y `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="68693-174">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="68693-175">Esta directiva no tiene ningún efecto a menos que una instancia de `Explicit` tenga definida una configuración de directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="68693-175">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="68693-176">Por ejemplo, si es el caso de `Explicit<Int32>`, se crea una instancia de `Implicit<Int32>` con sus miembros públicos enraizados, y sus metadatos se vuelven accesibles para programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="68693-176">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="68693-177">El siguiente es un ejemplo del mundo real en el que se aplica al menos un serializador.</span><span class="sxs-lookup"><span data-stu-id="68693-177">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="68693-178">Las directivas capturan el requisito de que el reflejo en algo escrito como `IList<` *algo* `>` también implica reflejar en el tipo de `List<` *elemento* correspondiente `>` sin necesidad de ninguna anotación por aplicación.</span><span class="sxs-lookup"><span data-stu-id="68693-178">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="68693-179">El elemento `<ImpliesType>` también puede aparecer dentro de un elemento `<Method>`, ya que en algunos casos crear instancias de un método genérico implica que se refleje en la creación de instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="68693-179">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="68693-180">Por ejemplo, imagine un método genérico `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` al que una determinada biblioteca tendrá acceso dinámicamente junto con los tipos asociados <xref:System.Collections.Generic.List%601> y <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="68693-180">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="68693-181">Esto puede expresarse como:</span><span class="sxs-lookup"><span data-stu-id="68693-181">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="68693-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="68693-182">See also</span></span>

- [<span data-ttu-id="68693-183">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="68693-183">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="68693-184">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="68693-184">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="68693-185">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="68693-185">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
