---
title: <GenericParameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40fef845a55412e5731ec08bd1e038d6b311694c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111662"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="856ce-102">\<GenericParameter > elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="856ce-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="856ce-103">Aplica la directiva al tipo de parámetro de un método o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="856ce-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="856ce-104">Syntax</span></span>  
  
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
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="856ce-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="856ce-105">Attributes and Elements</span></span>  
 <span data-ttu-id="856ce-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="856ce-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="856ce-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="856ce-107">Attributes</span></span>  
  
|<span data-ttu-id="856ce-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="856ce-108">Attribute</span></span>|<span data-ttu-id="856ce-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="856ce-109">Attribute type</span></span>|<span data-ttu-id="856ce-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="856ce-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="856ce-111">General</span><span class="sxs-lookup"><span data-stu-id="856ce-111">General</span></span>|<span data-ttu-id="856ce-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="856ce-112">Required attribute.</span></span> <span data-ttu-id="856ce-113">Nombre del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="856ce-113">The name of the generic parameter.</span></span> <span data-ttu-id="856ce-114">Por ejemplo, en el delegado genérico <xref:System.Func%603>, el valor del atributo `Name` es "TResult" para aplicar la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="856ce-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="856ce-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="856ce-115">Reflection</span></span>|<span data-ttu-id="856ce-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-116">Optional attribute.</span></span> <span data-ttu-id="856ce-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="856ce-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="856ce-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="856ce-118">Reflection</span></span>|<span data-ttu-id="856ce-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-119">Optional attribute.</span></span> <span data-ttu-id="856ce-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="856ce-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="856ce-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="856ce-121">Reflection</span></span>|<span data-ttu-id="856ce-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-122">Optional attribute.</span></span> <span data-ttu-id="856ce-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="856ce-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="856ce-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="856ce-124">Serialization</span></span>|<span data-ttu-id="856ce-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-125">Optional attribute.</span></span> <span data-ttu-id="856ce-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="856ce-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="856ce-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="856ce-127">Serialization</span></span>|<span data-ttu-id="856ce-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-128">Optional attribute.</span></span> <span data-ttu-id="856ce-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="856ce-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="856ce-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="856ce-130">Serialization</span></span>|<span data-ttu-id="856ce-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-131">Optional attribute.</span></span> <span data-ttu-id="856ce-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="856ce-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="856ce-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="856ce-133">Serialization</span></span>|<span data-ttu-id="856ce-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-134">Optional attribute.</span></span> <span data-ttu-id="856ce-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="856ce-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="856ce-136">Interop</span><span class="sxs-lookup"><span data-stu-id="856ce-136">Interop</span></span>|<span data-ttu-id="856ce-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-137">Optional attribute.</span></span> <span data-ttu-id="856ce-138">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="856ce-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="856ce-139">Interop</span><span class="sxs-lookup"><span data-stu-id="856ce-139">Interop</span></span>|<span data-ttu-id="856ce-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-140">Optional attribute.</span></span> <span data-ttu-id="856ce-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="856ce-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="856ce-142">Interop</span><span class="sxs-lookup"><span data-stu-id="856ce-142">Interop</span></span>|<span data-ttu-id="856ce-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="856ce-143">Optional attribute.</span></span> <span data-ttu-id="856ce-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="856ce-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="856ce-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="856ce-145">Name attribute</span></span>  
  
|<span data-ttu-id="856ce-146">Valor</span><span class="sxs-lookup"><span data-stu-id="856ce-146">Value</span></span>|<span data-ttu-id="856ce-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="856ce-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="856ce-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="856ce-148">*generic_parameter_name*</span></span>|<span data-ttu-id="856ce-149">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="856ce-149">Required attribute.</span></span> <span data-ttu-id="856ce-150">Nombre del parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="856ce-150">The name of the generic type parameter.</span></span> <span data-ttu-id="856ce-151">Por ejemplo, en el delegado genérico <xref:System.Func%603>, un valor *generic_parameter_name* de "TResult" aplica la directiva en tiempo de ejecución al valor devuelto del delegado.</span><span class="sxs-lookup"><span data-stu-id="856ce-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="856ce-152">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="856ce-152">All other attributes</span></span>  
  
|<span data-ttu-id="856ce-153">Valor</span><span class="sxs-lookup"><span data-stu-id="856ce-153">Value</span></span>|<span data-ttu-id="856ce-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="856ce-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="856ce-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="856ce-155">*policy_setting*</span></span>|<span data-ttu-id="856ce-156">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="856ce-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="856ce-157">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="856ce-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="856ce-158">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="856ce-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="856ce-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="856ce-159">Child Elements</span></span>  
 <span data-ttu-id="856ce-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="856ce-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="856ce-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="856ce-161">Parent Elements</span></span>  
  
|<span data-ttu-id="856ce-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="856ce-162">Element</span></span>|<span data-ttu-id="856ce-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="856ce-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="856ce-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="856ce-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="856ce-165">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="856ce-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="856ce-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="856ce-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="856ce-167">Aplica la directiva de reflexión en tiempo de ejecución a un tipo determinado, como una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="856ce-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="856ce-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="856ce-168">Remarks</span></span>  
 <span data-ttu-id="856ce-169">El elemento `<GenericParameter>` es un elemento secundario del elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) o [\<Type>](../../../docs/framework/net-native/type-element-net-native.md), y sirve para aplicar directivas a un parámetro de tipo genérico concreto especificado por su nombre en el tipo genérico o en la firma del método.</span><span class="sxs-lookup"><span data-stu-id="856ce-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="856ce-170">El elemento `<GenericParameter>` es de mayor utilidad cuando se usa con serializadores.</span><span class="sxs-lookup"><span data-stu-id="856ce-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="856ce-171">En el ejemplo siguiente se usa el elemento `<GenericParameter>` para aplicar una directiva al tipo `T` en llamadas a las sobrecargas de métodos [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) del serializador NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="856ce-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="856ce-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="856ce-172">See also</span></span>

- [<span data-ttu-id="856ce-173">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="856ce-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
- [<span data-ttu-id="856ce-174">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="856ce-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="856ce-175">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="856ce-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- <span data-ttu-id="856ce-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="856ce-176">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>
- [<span data-ttu-id="856ce-177">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="856ce-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
