---
title: Elemento &lt;Parameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 820c36abda104bbf748e5b3a7838f3c7715048e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltparametergt-element-net-native"></a><span data-ttu-id="45d45-102">Elemento &lt;Parameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="45d45-102">&lt;Parameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="45d45-103">Aplica la directiva de reflexión al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="45d45-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45d45-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45d45-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="45d45-105">Attributes and Elements</span></span>  
 <span data-ttu-id="45d45-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="45d45-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45d45-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="45d45-107">Attributes</span></span>  
  
|<span data-ttu-id="45d45-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="45d45-108">Attribute</span></span>|<span data-ttu-id="45d45-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="45d45-109">Attribute type</span></span>|<span data-ttu-id="45d45-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d45-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="45d45-111">General</span><span class="sxs-lookup"><span data-stu-id="45d45-111">General</span></span>|<span data-ttu-id="45d45-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="45d45-112">Required attribute.</span></span> <span data-ttu-id="45d45-113">Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="45d45-113">The parameter name.</span></span> <span data-ttu-id="45d45-114">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="45d45-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="45d45-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="45d45-115">Reflection</span></span>|<span data-ttu-id="45d45-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-116">Optional attribute.</span></span> <span data-ttu-id="45d45-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="45d45-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="45d45-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="45d45-118">Reflection</span></span>|<span data-ttu-id="45d45-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-119">Optional attribute.</span></span> <span data-ttu-id="45d45-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="45d45-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="45d45-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="45d45-121">Reflection</span></span>|<span data-ttu-id="45d45-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-122">Optional attribute.</span></span> <span data-ttu-id="45d45-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="45d45-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="45d45-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="45d45-124">Serialization</span></span>|<span data-ttu-id="45d45-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-125">Optional attribute.</span></span> <span data-ttu-id="45d45-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="45d45-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="45d45-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="45d45-127">Serialization</span></span>|<span data-ttu-id="45d45-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-128">Optional attribute.</span></span> <span data-ttu-id="45d45-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45d45-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="45d45-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="45d45-130">Serialization</span></span>|<span data-ttu-id="45d45-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-131">Optional attribute.</span></span> <span data-ttu-id="45d45-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45d45-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="45d45-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="45d45-133">Serialization</span></span>|<span data-ttu-id="45d45-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-134">Optional attribute.</span></span> <span data-ttu-id="45d45-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45d45-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="45d45-136">Interop</span><span class="sxs-lookup"><span data-stu-id="45d45-136">Interop</span></span>|<span data-ttu-id="45d45-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-137">Optional attribute.</span></span> <span data-ttu-id="45d45-138">Controla la directiva de serialización de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="45d45-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="45d45-139">Interop</span><span class="sxs-lookup"><span data-stu-id="45d45-139">Interop</span></span>|<span data-ttu-id="45d45-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-140">Optional attribute.</span></span> <span data-ttu-id="45d45-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="45d45-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="45d45-142">Interop</span><span class="sxs-lookup"><span data-stu-id="45d45-142">Interop</span></span>|<span data-ttu-id="45d45-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="45d45-143">Optional attribute.</span></span> <span data-ttu-id="45d45-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="45d45-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="45d45-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="45d45-145">Name attribute</span></span>  
  
|<span data-ttu-id="45d45-146">Valor</span><span class="sxs-lookup"><span data-stu-id="45d45-146">Value</span></span>|<span data-ttu-id="45d45-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d45-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45d45-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="45d45-148">*parameter_name*</span></span>|<span data-ttu-id="45d45-149">Nombre del parámetro de método al que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="45d45-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="45d45-150">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="45d45-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="45d45-151">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="45d45-151">All other attributes</span></span>  
  
|<span data-ttu-id="45d45-152">Valor</span><span class="sxs-lookup"><span data-stu-id="45d45-152">Value</span></span>|<span data-ttu-id="45d45-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d45-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="45d45-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="45d45-154">*policy_setting*</span></span>|<span data-ttu-id="45d45-155">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="45d45-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="45d45-156">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="45d45-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="45d45-157">Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="45d45-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45d45-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="45d45-158">Child Elements</span></span>  
 <span data-ttu-id="45d45-159">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="45d45-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45d45-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="45d45-160">Parent Elements</span></span>  
  
|<span data-ttu-id="45d45-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="45d45-161">Element</span></span>|<span data-ttu-id="45d45-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d45-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45d45-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="45d45-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="45d45-164">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o un método.</span><span class="sxs-lookup"><span data-stu-id="45d45-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45d45-165">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45d45-165">Remarks</span></span>  
 <span data-ttu-id="45d45-166">`<Parameter>` es un elemento secundario del elemento [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) y se usa para aplicar directivas a un parámetro de método concreto.</span><span class="sxs-lookup"><span data-stu-id="45d45-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="45d45-167">El parámetro de método determinado se especifica mediante el nombre en lugar del tipo.</span><span class="sxs-lookup"><span data-stu-id="45d45-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="45d45-168">Debe haber presente al menos un atributo que represente un tipo de directiva, como `Activate` o `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="45d45-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d45-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="45d45-169">See Also</span></span>  
 [<span data-ttu-id="45d45-170">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="45d45-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="45d45-171">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="45d45-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 <span data-ttu-id="45d45-172">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="45d45-172">[Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)</span></span>  
 [<span data-ttu-id="45d45-173">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="45d45-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
