---
description: 'Más información sobre: <Parameter> elemento (.net Native)'
title: <Parameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 53b84027e8393e0a799d9652767d173c2787cd27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662798"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="8d15e-103">\<Parameter> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="8d15e-103">\<Parameter> Element (.NET Native)</span></span>

<span data-ttu-id="8d15e-104">Aplica la directiva de reflexión al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="8d15e-104">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d15e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d15e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d15e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8d15e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8d15e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8d15e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d15e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8d15e-108">Attributes</span></span>  
  
|<span data-ttu-id="8d15e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d15e-109">Attribute</span></span>|<span data-ttu-id="8d15e-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="8d15e-110">Attribute type</span></span>|<span data-ttu-id="8d15e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d15e-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="8d15e-112">General</span><span class="sxs-lookup"><span data-stu-id="8d15e-112">General</span></span>|<span data-ttu-id="8d15e-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8d15e-113">Required attribute.</span></span> <span data-ttu-id="8d15e-114">Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d15e-114">The parameter name.</span></span> <span data-ttu-id="8d15e-115">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="8d15e-115">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="8d15e-116">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8d15e-116">Reflection</span></span>|<span data-ttu-id="8d15e-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-117">Optional attribute.</span></span> <span data-ttu-id="8d15e-118">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="8d15e-118">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="8d15e-119">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8d15e-119">Reflection</span></span>|<span data-ttu-id="8d15e-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-120">Optional attribute.</span></span> <span data-ttu-id="8d15e-121">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8d15e-121">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="8d15e-122">Reflexión</span><span class="sxs-lookup"><span data-stu-id="8d15e-122">Reflection</span></span>|<span data-ttu-id="8d15e-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-123">Optional attribute.</span></span> <span data-ttu-id="8d15e-124">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="8d15e-124">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="8d15e-125">Serialización</span><span class="sxs-lookup"><span data-stu-id="8d15e-125">Serialization</span></span>|<span data-ttu-id="8d15e-126">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-126">Optional attribute.</span></span> <span data-ttu-id="8d15e-127">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="8d15e-127">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="8d15e-128">Serialización</span><span class="sxs-lookup"><span data-stu-id="8d15e-128">Serialization</span></span>|<span data-ttu-id="8d15e-129">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-129">Optional attribute.</span></span> <span data-ttu-id="8d15e-130">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d15e-130">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="8d15e-131">Serialización</span><span class="sxs-lookup"><span data-stu-id="8d15e-131">Serialization</span></span>|<span data-ttu-id="8d15e-132">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-132">Optional attribute.</span></span> <span data-ttu-id="8d15e-133">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d15e-133">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="8d15e-134">Serialización</span><span class="sxs-lookup"><span data-stu-id="8d15e-134">Serialization</span></span>|<span data-ttu-id="8d15e-135">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-135">Optional attribute.</span></span> <span data-ttu-id="8d15e-136">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8d15e-136">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="8d15e-137">Interop</span><span class="sxs-lookup"><span data-stu-id="8d15e-137">Interop</span></span>|<span data-ttu-id="8d15e-138">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-138">Optional attribute.</span></span> <span data-ttu-id="8d15e-139">Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="8d15e-139">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="8d15e-140">Interop</span><span class="sxs-lookup"><span data-stu-id="8d15e-140">Interop</span></span>|<span data-ttu-id="8d15e-141">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-141">Optional attribute.</span></span> <span data-ttu-id="8d15e-142">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="8d15e-142">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="8d15e-143">Interop</span><span class="sxs-lookup"><span data-stu-id="8d15e-143">Interop</span></span>|<span data-ttu-id="8d15e-144">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="8d15e-144">Optional attribute.</span></span> <span data-ttu-id="8d15e-145">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="8d15e-145">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="8d15e-146">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="8d15e-146">Name attribute</span></span>  
  
|<span data-ttu-id="8d15e-147">Value</span><span class="sxs-lookup"><span data-stu-id="8d15e-147">Value</span></span>|<span data-ttu-id="8d15e-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d15e-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d15e-149">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="8d15e-149">*parameter_name*</span></span>|<span data-ttu-id="8d15e-150">Nombre del parámetro de método al que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="8d15e-150">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="8d15e-151">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="8d15e-151">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="8d15e-152">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="8d15e-152">All other attributes</span></span>  
  
|<span data-ttu-id="8d15e-153">Value</span><span class="sxs-lookup"><span data-stu-id="8d15e-153">Value</span></span>|<span data-ttu-id="8d15e-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d15e-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d15e-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="8d15e-155">*policy_setting*</span></span>|<span data-ttu-id="8d15e-156">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="8d15e-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="8d15e-157">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="8d15e-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="8d15e-158">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="8d15e-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d15e-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8d15e-159">Child Elements</span></span>  

 <span data-ttu-id="8d15e-160">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8d15e-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d15e-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8d15e-161">Parent Elements</span></span>  
  
|<span data-ttu-id="8d15e-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="8d15e-162">Element</span></span>|<span data-ttu-id="8d15e-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d15e-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="8d15e-164">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="8d15e-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d15e-165">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d15e-165">Remarks</span></span>  

 <span data-ttu-id="8d15e-166">El `<Parameter>` elemento es un elemento secundario del [\<Method>](method-element-net-native.md) elemento y se utiliza para aplicar la Directiva a un parámetro de método determinado.</span><span class="sxs-lookup"><span data-stu-id="8d15e-166">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="8d15e-167">El parámetro de método determinado se especifica mediante el nombre en lugar del tipo.</span><span class="sxs-lookup"><span data-stu-id="8d15e-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="8d15e-168">Debe haber presente al menos un atributo que represente un tipo de directiva, como `Activate` o `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="8d15e-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d15e-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d15e-169">See also</span></span>

- [<span data-ttu-id="8d15e-170">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="8d15e-170">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="8d15e-171">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="8d15e-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="8d15e-172">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8d15e-172">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="8d15e-173">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8d15e-173">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
