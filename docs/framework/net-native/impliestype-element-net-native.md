---
title: Elemento <ImpliesType> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 2f0ce1a1587e190627212cba07db298c12f4b30e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128390"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="94a9e-102">\<elemento > ImpliesType (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="94a9e-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="94a9e-103">Aplica una directiva a un tipo, si dicha directiva se ha aplicado al tipo contenedor o al método.</span><span class="sxs-lookup"><span data-stu-id="94a9e-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a9e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94a9e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94a9e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="94a9e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="94a9e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="94a9e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94a9e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="94a9e-107">Attributes</span></span>  
  
|<span data-ttu-id="94a9e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="94a9e-108">Attribute</span></span>|<span data-ttu-id="94a9e-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="94a9e-109">Attribute type</span></span>|<span data-ttu-id="94a9e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="94a9e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="94a9e-111">General</span><span class="sxs-lookup"><span data-stu-id="94a9e-111">General</span></span>|<span data-ttu-id="94a9e-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="94a9e-112">Required attribute.</span></span> <span data-ttu-id="94a9e-113">Especifica el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="94a9e-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="94a9e-114">Reflection</span></span>|<span data-ttu-id="94a9e-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-115">Optional attribute.</span></span> <span data-ttu-id="94a9e-116">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="94a9e-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="94a9e-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="94a9e-117">Reflection</span></span>|<span data-ttu-id="94a9e-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-118">Optional attribute.</span></span> <span data-ttu-id="94a9e-119">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="94a9e-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="94a9e-120">Reflexión</span><span class="sxs-lookup"><span data-stu-id="94a9e-120">Reflection</span></span>|<span data-ttu-id="94a9e-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-121">Optional attribute.</span></span> <span data-ttu-id="94a9e-122">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="94a9e-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="94a9e-123">Serialización</span><span class="sxs-lookup"><span data-stu-id="94a9e-123">Serialization</span></span>|<span data-ttu-id="94a9e-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-124">Optional attribute.</span></span> <span data-ttu-id="94a9e-125">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="94a9e-126">Serialización</span><span class="sxs-lookup"><span data-stu-id="94a9e-126">Serialization</span></span>|<span data-ttu-id="94a9e-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-127">Optional attribute.</span></span> <span data-ttu-id="94a9e-128">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94a9e-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="94a9e-129">Serialización</span><span class="sxs-lookup"><span data-stu-id="94a9e-129">Serialization</span></span>|<span data-ttu-id="94a9e-130">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-130">Optional attribute.</span></span> <span data-ttu-id="94a9e-131">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94a9e-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="94a9e-132">Serialización</span><span class="sxs-lookup"><span data-stu-id="94a9e-132">Serialization</span></span>|<span data-ttu-id="94a9e-133">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-133">Optional attribute.</span></span> <span data-ttu-id="94a9e-134">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94a9e-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="94a9e-135">Interop</span><span class="sxs-lookup"><span data-stu-id="94a9e-135">Interop</span></span>|<span data-ttu-id="94a9e-136">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-136">Optional attribute.</span></span> <span data-ttu-id="94a9e-137">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="94a9e-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="94a9e-138">Interop</span><span class="sxs-lookup"><span data-stu-id="94a9e-138">Interop</span></span>|<span data-ttu-id="94a9e-139">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-139">Optional attribute.</span></span> <span data-ttu-id="94a9e-140">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="94a9e-141">Interop</span><span class="sxs-lookup"><span data-stu-id="94a9e-141">Interop</span></span>|<span data-ttu-id="94a9e-142">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="94a9e-142">Optional attribute.</span></span> <span data-ttu-id="94a9e-143">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="94a9e-144">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="94a9e-144">Name attribute</span></span>  
  
|<span data-ttu-id="94a9e-145">Valor</span><span class="sxs-lookup"><span data-stu-id="94a9e-145">Value</span></span>|<span data-ttu-id="94a9e-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="94a9e-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94a9e-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="94a9e-147">*type_name*</span></span>|<span data-ttu-id="94a9e-148">Nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-148">The type name.</span></span> <span data-ttu-id="94a9e-149">Si el tipo representado por este elemento `<ImpliesType>` se encuentra en el mismo espacio de nombres que su elemento contenedor `<Type>`, *type_name* puede incluir el nombre del tipo sin su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="94a9e-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="94a9e-150">De lo contrario, *type_name* debe incluir el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="94a9e-151">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="94a9e-151">All other attributes</span></span>  
  
|<span data-ttu-id="94a9e-152">Valor</span><span class="sxs-lookup"><span data-stu-id="94a9e-152">Value</span></span>|<span data-ttu-id="94a9e-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="94a9e-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="94a9e-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="94a9e-154">*policy_setting*</span></span>|<span data-ttu-id="94a9e-155">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="94a9e-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="94a9e-156">Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="94a9e-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="94a9e-157">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="94a9e-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94a9e-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="94a9e-158">Child Elements</span></span>  
 <span data-ttu-id="94a9e-159">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="94a9e-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94a9e-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="94a9e-160">Parent Elements</span></span>  
  
|<span data-ttu-id="94a9e-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="94a9e-161">Element</span></span>|<span data-ttu-id="94a9e-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="94a9e-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94a9e-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="94a9e-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="94a9e-164">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="94a9e-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="94a9e-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="94a9e-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="94a9e-166">Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="94a9e-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="94a9e-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="94a9e-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="94a9e-168">Aplica la directiva de reflexión a un método.</span><span class="sxs-lookup"><span data-stu-id="94a9e-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94a9e-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94a9e-169">Remarks</span></span>  
 <span data-ttu-id="94a9e-170">El elemento `<ImpliesType>` sirve principalmente para que lo utilicen las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="94a9e-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="94a9e-171">Está pensado para el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="94a9e-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="94a9e-172">Si una rutina debe reflejarse en un determinado tipo, necesariamente debe reflejarse en un segundo tipo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="94a9e-173">Los metadatos para la creación de instancias implícita del segundo tipo no está disponible, ya que el análisis estático no indica si es necesario.</span><span class="sxs-lookup"><span data-stu-id="94a9e-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="94a9e-174">Normalmente, los dos tipos son instancias genéricas con argumentos de tipo compartido.</span><span class="sxs-lookup"><span data-stu-id="94a9e-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="94a9e-175">El elemento `<ImpliesType>` se definió con la suposición de que una necesidad de reflexión en el tipo especificado por su elemento primario implica una necesidad de reflexión en el tipo especificado por el elemento `<ImpliesType>`.</span><span class="sxs-lookup"><span data-stu-id="94a9e-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="94a9e-176">Por ejemplo, las siguientes directivas de reflexión se aplican en dos tipos, `Explicit<T>` y `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="94a9e-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="94a9e-177">Esta directiva no tiene ningún efecto a menos que una instancia de `Explicit` tenga definida una configuración de directiva `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="94a9e-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="94a9e-178">Por ejemplo, si es el caso de `Explicit<Int32>`, se crea una instancia de `Implicit<Int32>` con sus miembros públicos enraizados, y sus metadatos se vuelven accesibles para programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="94a9e-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="94a9e-179">El siguiente es un ejemplo del mundo real en el que se aplica al menos un serializador.</span><span class="sxs-lookup"><span data-stu-id="94a9e-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="94a9e-180">Las directivas recogen el requisito de que el reflejo en algo tipado como `IList<`*something*`>` también implica un reflejo en el tipo `List<`*something*`>` correspondiente sin necesidad de exigir ninguna anotación por aplicación.</span><span class="sxs-lookup"><span data-stu-id="94a9e-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="94a9e-181">El elemento `<ImpliesType>` también puede aparecer dentro de un elemento `<Method>`, ya que en algunos casos crear instancias de un método genérico implica que se refleje en la creación de instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="94a9e-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="94a9e-182">Por ejemplo, Imagine un método genérico `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` que una determinada biblioteca tendrá acceso dinámicamente junto con los tipos asociados <xref:System.Collections.Generic.List%601> y <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="94a9e-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="94a9e-183">Esto puede expresarse como:</span><span class="sxs-lookup"><span data-stu-id="94a9e-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94a9e-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="94a9e-184">See also</span></span>

- <span data-ttu-id="94a9e-185">[Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución [rd.xml])</span><span class="sxs-lookup"><span data-stu-id="94a9e-185">[Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md)</span></span>
- [<span data-ttu-id="94a9e-186">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="94a9e-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- <span data-ttu-id="94a9e-187">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="94a9e-187">[Runtime Directive Policy Settings](runtime-directive-policy-settings.md)</span></span>
