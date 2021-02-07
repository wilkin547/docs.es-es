---
description: 'Más información sobre: <GenericParameter> elemento (.net Native)'
title: <GenericParameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: 57cbb3418289d7da4f25577188299acd55ce6c94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747834"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="bf4eb-103">\<GenericParameter> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="bf4eb-103">\<GenericParameter> Element (.NET Native)</span></span>

<span data-ttu-id="bf4eb-104">Aplica la directiva al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-104">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf4eb-105">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf4eb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf4eb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bf4eb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf4eb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf4eb-108">Attributes</span></span>  
  
|<span data-ttu-id="bf4eb-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="bf4eb-109">Attribute</span></span>|<span data-ttu-id="bf4eb-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="bf4eb-110">Attribute type</span></span>|<span data-ttu-id="bf4eb-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf4eb-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="bf4eb-112">General</span><span class="sxs-lookup"><span data-stu-id="bf4eb-112">General</span></span>|<span data-ttu-id="bf4eb-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-113">Required attribute.</span></span> <span data-ttu-id="bf4eb-114">Nombre del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-114">The name of the generic parameter.</span></span> <span data-ttu-id="bf4eb-115">Por ejemplo, en el delegado genérico <xref:System.Func%603>, el valor del atributo `Name` es "TResult" para aplicar la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-115">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="bf4eb-116">Reflexión</span><span class="sxs-lookup"><span data-stu-id="bf4eb-116">Reflection</span></span>|<span data-ttu-id="bf4eb-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-117">Optional attribute.</span></span> <span data-ttu-id="bf4eb-118">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-118">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="bf4eb-119">Reflexión</span><span class="sxs-lookup"><span data-stu-id="bf4eb-119">Reflection</span></span>|<span data-ttu-id="bf4eb-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-120">Optional attribute.</span></span> <span data-ttu-id="bf4eb-121">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-121">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="bf4eb-122">Reflexión</span><span class="sxs-lookup"><span data-stu-id="bf4eb-122">Reflection</span></span>|<span data-ttu-id="bf4eb-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-123">Optional attribute.</span></span> <span data-ttu-id="bf4eb-124">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-124">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="bf4eb-125">Serialización</span><span class="sxs-lookup"><span data-stu-id="bf4eb-125">Serialization</span></span>|<span data-ttu-id="bf4eb-126">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-126">Optional attribute.</span></span> <span data-ttu-id="bf4eb-127">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-127">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="bf4eb-128">Serialización</span><span class="sxs-lookup"><span data-stu-id="bf4eb-128">Serialization</span></span>|<span data-ttu-id="bf4eb-129">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-129">Optional attribute.</span></span> <span data-ttu-id="bf4eb-130">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-130">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="bf4eb-131">Serialización</span><span class="sxs-lookup"><span data-stu-id="bf4eb-131">Serialization</span></span>|<span data-ttu-id="bf4eb-132">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-132">Optional attribute.</span></span> <span data-ttu-id="bf4eb-133">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-133">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="bf4eb-134">Serialización</span><span class="sxs-lookup"><span data-stu-id="bf4eb-134">Serialization</span></span>|<span data-ttu-id="bf4eb-135">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-135">Optional attribute.</span></span> <span data-ttu-id="bf4eb-136">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-136">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="bf4eb-137">Interop</span><span class="sxs-lookup"><span data-stu-id="bf4eb-137">Interop</span></span>|<span data-ttu-id="bf4eb-138">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-138">Optional attribute.</span></span> <span data-ttu-id="bf4eb-139">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-139">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="bf4eb-140">Interop</span><span class="sxs-lookup"><span data-stu-id="bf4eb-140">Interop</span></span>|<span data-ttu-id="bf4eb-141">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-141">Optional attribute.</span></span> <span data-ttu-id="bf4eb-142">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-142">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="bf4eb-143">Interop</span><span class="sxs-lookup"><span data-stu-id="bf4eb-143">Interop</span></span>|<span data-ttu-id="bf4eb-144">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-144">Optional attribute.</span></span> <span data-ttu-id="bf4eb-145">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-145">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="bf4eb-146">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="bf4eb-146">Name attribute</span></span>  
  
|<span data-ttu-id="bf4eb-147">Value</span><span class="sxs-lookup"><span data-stu-id="bf4eb-147">Value</span></span>|<span data-ttu-id="bf4eb-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf4eb-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bf4eb-149">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="bf4eb-149">*generic_parameter_name*</span></span>|<span data-ttu-id="bf4eb-150">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-150">Required attribute.</span></span> <span data-ttu-id="bf4eb-151">Nombre del parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-151">The name of the generic type parameter.</span></span> <span data-ttu-id="bf4eb-152">Por ejemplo, en el delegado genérico <xref:System.Func%603>, un valor *generic_parameter_name* de "TResult" aplica la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-152">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="bf4eb-153">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="bf4eb-153">All other attributes</span></span>  
  
|<span data-ttu-id="bf4eb-154">Value</span><span class="sxs-lookup"><span data-stu-id="bf4eb-154">Value</span></span>|<span data-ttu-id="bf4eb-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf4eb-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bf4eb-156">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="bf4eb-156">*policy_setting*</span></span>|<span data-ttu-id="bf4eb-157">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-157">The setting to apply to this policy type.</span></span> <span data-ttu-id="bf4eb-158">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-158">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="bf4eb-159">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="bf4eb-159">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf4eb-160">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf4eb-160">Child Elements</span></span>  

 <span data-ttu-id="bf4eb-161">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf4eb-162">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf4eb-162">Parent Elements</span></span>  
  
|<span data-ttu-id="bf4eb-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf4eb-163">Element</span></span>|<span data-ttu-id="bf4eb-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf4eb-164">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="bf4eb-165">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="bf4eb-166">Aplica la directiva de reflexión en tiempo de ejecución a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-166">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf4eb-167">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf4eb-167">Remarks</span></span>  

 <span data-ttu-id="bf4eb-168">El `<GenericParameter>` elemento es un elemento secundario del [\<Method>](method-element-net-native.md) elemento o [\<Type>](type-element-net-native.md) y se utiliza para aplicar la Directiva a un parámetro de tipo genérico determinado, que se especifica mediante su nombre en el tipo genérico o en la firma del método.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-168">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="bf4eb-169">El elemento `<GenericParameter>` es de mayor utilidad cuando se usa con serializadores.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-169">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="bf4eb-170">En el ejemplo siguiente se usa el `<GenericParameter>` elemento para aplicar la Directiva al tipo `T` en las llamadas a las sobrecargas del método [JsonConvert. DeserializeObject \<T> (String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) del serializador JSON de NewtonSoft.</span><span class="sxs-lookup"><span data-stu-id="bf4eb-170">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf4eb-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf4eb-171">See also</span></span>

- [<span data-ttu-id="bf4eb-172">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="bf4eb-172">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="bf4eb-173">Elemento \<Type></span><span class="sxs-lookup"><span data-stu-id="bf4eb-173">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="bf4eb-174">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="bf4eb-174">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="bf4eb-175">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bf4eb-175">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="bf4eb-176">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bf4eb-176">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
