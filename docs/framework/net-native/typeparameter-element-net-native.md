---
description: 'Más información sobre: <TypeParameter> elemento (.net Native)'
title: <TypeParameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: 182cd62dc0584991b8ef0f5757d6005173d6d7a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803651"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="0c73d-103">\<TypeParameter> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0c73d-103">\<TypeParameter> Element (.NET Native)</span></span>

<span data-ttu-id="0c73d-104">Aplica la directiva al tipo representado por un argumento de tipo pasado a un método.</span><span class="sxs-lookup"><span data-stu-id="0c73d-104">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c73d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c73d-105">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c73d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c73d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0c73d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c73d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c73d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c73d-108">Attributes</span></span>  
  
|<span data-ttu-id="0c73d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0c73d-109">Attribute</span></span>|<span data-ttu-id="0c73d-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="0c73d-110">Attribute type</span></span>|<span data-ttu-id="0c73d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c73d-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0c73d-112">General</span><span class="sxs-lookup"><span data-stu-id="0c73d-112">General</span></span>|<span data-ttu-id="0c73d-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0c73d-113">Required attribute.</span></span> <span data-ttu-id="0c73d-114">Nombre del parámetro de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="0c73d-114">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="0c73d-115">Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="0c73d-115">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="0c73d-116">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c73d-116">Reflection</span></span>|<span data-ttu-id="0c73d-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-117">Optional attribute.</span></span> <span data-ttu-id="0c73d-118">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="0c73d-118">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0c73d-119">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c73d-119">Reflection</span></span>|<span data-ttu-id="0c73d-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-120">Optional attribute.</span></span> <span data-ttu-id="0c73d-121">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c73d-121">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0c73d-122">Reflexión</span><span class="sxs-lookup"><span data-stu-id="0c73d-122">Reflection</span></span>|<span data-ttu-id="0c73d-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-123">Optional attribute.</span></span> <span data-ttu-id="0c73d-124">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="0c73d-124">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0c73d-125">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c73d-125">Serialization</span></span>|<span data-ttu-id="0c73d-126">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-126">Optional attribute.</span></span> <span data-ttu-id="0c73d-127">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c73d-127">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0c73d-128">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c73d-128">Serialization</span></span>|<span data-ttu-id="0c73d-129">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-129">Optional attribute.</span></span> <span data-ttu-id="0c73d-130">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c73d-130">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0c73d-131">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c73d-131">Serialization</span></span>|<span data-ttu-id="0c73d-132">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-132">Optional attribute.</span></span> <span data-ttu-id="0c73d-133">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c73d-133">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0c73d-134">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c73d-134">Serialization</span></span>|<span data-ttu-id="0c73d-135">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-135">Optional attribute.</span></span> <span data-ttu-id="0c73d-136">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c73d-136">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0c73d-137">Interop</span><span class="sxs-lookup"><span data-stu-id="0c73d-137">Interop</span></span>|<span data-ttu-id="0c73d-138">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-138">Optional attribute.</span></span> <span data-ttu-id="0c73d-139">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="0c73d-139">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0c73d-140">Interop</span><span class="sxs-lookup"><span data-stu-id="0c73d-140">Interop</span></span>|<span data-ttu-id="0c73d-141">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-141">Optional attribute.</span></span> <span data-ttu-id="0c73d-142">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="0c73d-142">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0c73d-143">Interop</span><span class="sxs-lookup"><span data-stu-id="0c73d-143">Interop</span></span>|<span data-ttu-id="0c73d-144">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0c73d-144">Optional attribute.</span></span> <span data-ttu-id="0c73d-145">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="0c73d-145">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0c73d-146">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="0c73d-146">Name attribute</span></span>  
  
|<span data-ttu-id="0c73d-147">Value</span><span class="sxs-lookup"><span data-stu-id="0c73d-147">Value</span></span>|<span data-ttu-id="0c73d-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c73d-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c73d-149">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="0c73d-149">*parameter_name*</span></span>|<span data-ttu-id="0c73d-150">Nombre del parámetro de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="0c73d-150">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="0c73d-151">Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".</span><span class="sxs-lookup"><span data-stu-id="0c73d-151">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0c73d-152">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="0c73d-152">All other attributes</span></span>  
  
|<span data-ttu-id="0c73d-153">Value</span><span class="sxs-lookup"><span data-stu-id="0c73d-153">Value</span></span>|<span data-ttu-id="0c73d-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c73d-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c73d-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0c73d-155">*policy_setting*</span></span>|<span data-ttu-id="0c73d-156">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="0c73d-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="0c73d-157">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="0c73d-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0c73d-158">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="0c73d-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c73d-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c73d-159">Child Elements</span></span>  

 <span data-ttu-id="0c73d-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0c73d-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c73d-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c73d-161">Parent Elements</span></span>  
  
|<span data-ttu-id="0c73d-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c73d-162">Element</span></span>|<span data-ttu-id="0c73d-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c73d-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="0c73d-164">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="0c73d-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c73d-165">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c73d-165">Remarks</span></span>  

 <span data-ttu-id="0c73d-166">El `<TypeParameter>` elemento es similar al [\<Parameter>](parameter-element-net-native.md) elemento, salvo que solo se puede aplicar a parámetros de tipo <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="0c73d-166">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="0c73d-167">Aplica la directiva a cualquier tipo que se represente en tiempo de ejecución mediante el argumento de tipo especificado por el atributo `Name`.</span><span class="sxs-lookup"><span data-stu-id="0c73d-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="0c73d-168">Por ejemplo, el serializador JSON NewtonSoft incluye un método `JsonConvert.DeserializeObject(String value, Type type)` estático.</span><span class="sxs-lookup"><span data-stu-id="0c73d-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="0c73d-169">Las siguientes directivas de reflexión:</span><span class="sxs-lookup"><span data-stu-id="0c73d-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="0c73d-170">especifican que debe haber disponibles metadatos para el tipo en tiempo de ejecución representado por el argumento `type` para poder realizar la serialización.</span><span class="sxs-lookup"><span data-stu-id="0c73d-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="0c73d-171">Si estas directivas en tiempo de ejecución se aplican a un proyecto que incluye el siguiente código fuente:</span><span class="sxs-lookup"><span data-stu-id="0c73d-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="0c73d-172">las directivas de reflexión hacen que haya metadatos disponibles para el tipo `StockQuote` para el serializador JSON NewtonSoft en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c73d-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c73d-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c73d-173">See also</span></span>

- [<span data-ttu-id="0c73d-174">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="0c73d-174">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="0c73d-175">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0c73d-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0c73d-176">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c73d-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="0c73d-177">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c73d-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
