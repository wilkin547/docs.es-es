---
title: Elemento &lt;GenericParameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c682c75d4be78e9219a32e2a92520e9f9bfff823
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="221a0-102">Elemento &lt;GenericParameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="221a0-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="221a0-103">Aplica la directiva al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="221a0-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="221a0-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="221a0-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="221a0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="221a0-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="221a0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="221a0-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="221a0-107">Attributes</span></span>  
  
|<span data-ttu-id="221a0-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="221a0-108">Attribute</span></span>|<span data-ttu-id="221a0-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="221a0-109">Attribute type</span></span>|<span data-ttu-id="221a0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="221a0-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="221a0-111">General</span><span class="sxs-lookup"><span data-stu-id="221a0-111">General</span></span>|<span data-ttu-id="221a0-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="221a0-112">Required attribute.</span></span> <span data-ttu-id="221a0-113">Nombre del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="221a0-113">The name of the generic parameter.</span></span> <span data-ttu-id="221a0-114">Por ejemplo, en el delegado genérico <xref:System.Func%603>, el valor del atributo `Name` es "TResult" para aplicar la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="221a0-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="221a0-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="221a0-115">Reflection</span></span>|<span data-ttu-id="221a0-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-116">Optional attribute.</span></span> <span data-ttu-id="221a0-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="221a0-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="221a0-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="221a0-118">Reflection</span></span>|<span data-ttu-id="221a0-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-119">Optional attribute.</span></span> <span data-ttu-id="221a0-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="221a0-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="221a0-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="221a0-121">Reflection</span></span>|<span data-ttu-id="221a0-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-122">Optional attribute.</span></span> <span data-ttu-id="221a0-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="221a0-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="221a0-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="221a0-124">Serialization</span></span>|<span data-ttu-id="221a0-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-125">Optional attribute.</span></span> <span data-ttu-id="221a0-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="221a0-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="221a0-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="221a0-127">Serialization</span></span>|<span data-ttu-id="221a0-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-128">Optional attribute.</span></span> <span data-ttu-id="221a0-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="221a0-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="221a0-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="221a0-130">Serialization</span></span>|<span data-ttu-id="221a0-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-131">Optional attribute.</span></span> <span data-ttu-id="221a0-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="221a0-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="221a0-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="221a0-133">Serialization</span></span>|<span data-ttu-id="221a0-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-134">Optional attribute.</span></span> <span data-ttu-id="221a0-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="221a0-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="221a0-136">Interop</span><span class="sxs-lookup"><span data-stu-id="221a0-136">Interop</span></span>|<span data-ttu-id="221a0-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-137">Optional attribute.</span></span> <span data-ttu-id="221a0-138">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="221a0-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="221a0-139">Interop</span><span class="sxs-lookup"><span data-stu-id="221a0-139">Interop</span></span>|<span data-ttu-id="221a0-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-140">Optional attribute.</span></span> <span data-ttu-id="221a0-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="221a0-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="221a0-142">Interop</span><span class="sxs-lookup"><span data-stu-id="221a0-142">Interop</span></span>|<span data-ttu-id="221a0-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="221a0-143">Optional attribute.</span></span> <span data-ttu-id="221a0-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="221a0-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="221a0-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="221a0-145">Name attribute</span></span>  
  
|<span data-ttu-id="221a0-146">Valor</span><span class="sxs-lookup"><span data-stu-id="221a0-146">Value</span></span>|<span data-ttu-id="221a0-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="221a0-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="221a0-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="221a0-148">*generic_parameter_name*</span></span>|<span data-ttu-id="221a0-149">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="221a0-149">Required attribute.</span></span> <span data-ttu-id="221a0-150">Nombre del parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="221a0-150">The name of the generic type parameter.</span></span> <span data-ttu-id="221a0-151">Por ejemplo, en el delegado genérico <xref:System.Func%603>, un valor *generic_parameter_name* de "TResult" aplica la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="221a0-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="221a0-152">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="221a0-152">All other attributes</span></span>  
  
|<span data-ttu-id="221a0-153">Valor</span><span class="sxs-lookup"><span data-stu-id="221a0-153">Value</span></span>|<span data-ttu-id="221a0-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="221a0-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="221a0-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="221a0-155">*policy_setting*</span></span>|<span data-ttu-id="221a0-156">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="221a0-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="221a0-157">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="221a0-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="221a0-158">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="221a0-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="221a0-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="221a0-159">Child Elements</span></span>  
 <span data-ttu-id="221a0-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="221a0-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="221a0-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="221a0-161">Parent Elements</span></span>  
  
|<span data-ttu-id="221a0-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="221a0-162">Element</span></span>|<span data-ttu-id="221a0-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="221a0-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="221a0-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="221a0-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="221a0-165">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o un método.</span><span class="sxs-lookup"><span data-stu-id="221a0-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="221a0-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="221a0-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="221a0-167">Aplica la directiva de reflexión en tiempo de ejecución a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="221a0-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="221a0-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="221a0-168">Remarks</span></span>  
 <span data-ttu-id="221a0-169">El elemento `<GenericParameter>` es un elemento secundario del elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) o [\<Type>](../../../docs/framework/net-native/type-element-net-native.md), y sirve para aplicar directivas a un parámetro de tipo genérico concreto especificado por su nombre en el tipo genérico o en la firma del método.</span><span class="sxs-lookup"><span data-stu-id="221a0-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="221a0-170">El elemento `<GenericParameter>` es de mayor utilidad cuando se usa con serializadores.</span><span class="sxs-lookup"><span data-stu-id="221a0-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="221a0-171">En el ejemplo siguiente se usa el elemento `<GenericParameter>` para aplicar una directiva al tipo `T` en llamadas a las sobrecargas de métodos [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) del serializador NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="221a0-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="221a0-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="221a0-172">See Also</span></span>  
 [<span data-ttu-id="221a0-173">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="221a0-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="221a0-174">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="221a0-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="221a0-175">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="221a0-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 <span data-ttu-id="221a0-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="221a0-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>  
 [<span data-ttu-id="221a0-177">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="221a0-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
