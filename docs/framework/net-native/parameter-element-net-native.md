---
title: <Parameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 7e812ab60eb0a89eb868346733a8ea74e2f76d3e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287870"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="ee01e-102">\<Parameter> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="ee01e-102">\<Parameter> Element (.NET Native)</span></span>

<span data-ttu-id="ee01e-103">Aplica la directiva de reflexión al tipo del argumento que se pasa a un método.</span><span class="sxs-lookup"><span data-stu-id="ee01e-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee01e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee01e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee01e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ee01e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ee01e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ee01e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee01e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ee01e-107">Attributes</span></span>  
  
|<span data-ttu-id="ee01e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ee01e-108">Attribute</span></span>|<span data-ttu-id="ee01e-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="ee01e-109">Attribute type</span></span>|<span data-ttu-id="ee01e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee01e-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="ee01e-111">General</span><span class="sxs-lookup"><span data-stu-id="ee01e-111">General</span></span>|<span data-ttu-id="ee01e-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ee01e-112">Required attribute.</span></span> <span data-ttu-id="ee01e-113">Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ee01e-113">The parameter name.</span></span> <span data-ttu-id="ee01e-114">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="ee01e-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="ee01e-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ee01e-115">Reflection</span></span>|<span data-ttu-id="ee01e-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-116">Optional attribute.</span></span> <span data-ttu-id="ee01e-117">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="ee01e-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="ee01e-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ee01e-118">Reflection</span></span>|<span data-ttu-id="ee01e-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-119">Optional attribute.</span></span> <span data-ttu-id="ee01e-120">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee01e-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="ee01e-121">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ee01e-121">Reflection</span></span>|<span data-ttu-id="ee01e-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-122">Optional attribute.</span></span> <span data-ttu-id="ee01e-123">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="ee01e-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="ee01e-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="ee01e-124">Serialization</span></span>|<span data-ttu-id="ee01e-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-125">Optional attribute.</span></span> <span data-ttu-id="ee01e-126">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="ee01e-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="ee01e-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="ee01e-127">Serialization</span></span>|<span data-ttu-id="ee01e-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-128">Optional attribute.</span></span> <span data-ttu-id="ee01e-129">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee01e-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="ee01e-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="ee01e-130">Serialization</span></span>|<span data-ttu-id="ee01e-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-131">Optional attribute.</span></span> <span data-ttu-id="ee01e-132">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee01e-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="ee01e-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="ee01e-133">Serialization</span></span>|<span data-ttu-id="ee01e-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-134">Optional attribute.</span></span> <span data-ttu-id="ee01e-135">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee01e-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="ee01e-136">Interop</span><span class="sxs-lookup"><span data-stu-id="ee01e-136">Interop</span></span>|<span data-ttu-id="ee01e-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-137">Optional attribute.</span></span> <span data-ttu-id="ee01e-138">Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.</span><span class="sxs-lookup"><span data-stu-id="ee01e-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="ee01e-139">Interop</span><span class="sxs-lookup"><span data-stu-id="ee01e-139">Interop</span></span>|<span data-ttu-id="ee01e-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-140">Optional attribute.</span></span> <span data-ttu-id="ee01e-141">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="ee01e-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="ee01e-142">Interop</span><span class="sxs-lookup"><span data-stu-id="ee01e-142">Interop</span></span>|<span data-ttu-id="ee01e-143">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ee01e-143">Optional attribute.</span></span> <span data-ttu-id="ee01e-144">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="ee01e-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="ee01e-145">Name (atributo)</span><span class="sxs-lookup"><span data-stu-id="ee01e-145">Name attribute</span></span>  
  
|<span data-ttu-id="ee01e-146">Valor</span><span class="sxs-lookup"><span data-stu-id="ee01e-146">Value</span></span>|<span data-ttu-id="ee01e-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee01e-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee01e-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="ee01e-148">*parameter_name*</span></span>|<span data-ttu-id="ee01e-149">Nombre del parámetro de método al que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="ee01e-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="ee01e-150">Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".</span><span class="sxs-lookup"><span data-stu-id="ee01e-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="ee01e-151">Resto de atributos</span><span class="sxs-lookup"><span data-stu-id="ee01e-151">All other attributes</span></span>  
  
|<span data-ttu-id="ee01e-152">Valor</span><span class="sxs-lookup"><span data-stu-id="ee01e-152">Value</span></span>|<span data-ttu-id="ee01e-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee01e-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee01e-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="ee01e-154">*policy_setting*</span></span>|<span data-ttu-id="ee01e-155">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="ee01e-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="ee01e-156">Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="ee01e-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="ee01e-157">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="ee01e-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee01e-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ee01e-158">Child Elements</span></span>  

 <span data-ttu-id="ee01e-159">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ee01e-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee01e-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ee01e-160">Parent Elements</span></span>  
  
|<span data-ttu-id="ee01e-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee01e-161">Element</span></span>|<span data-ttu-id="ee01e-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee01e-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="ee01e-163">Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.</span><span class="sxs-lookup"><span data-stu-id="ee01e-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee01e-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee01e-164">Remarks</span></span>  

 <span data-ttu-id="ee01e-165">El `<Parameter>` elemento es un elemento secundario del [\<Method>](method-element-net-native.md) elemento y se utiliza para aplicar la Directiva a un parámetro de método determinado.</span><span class="sxs-lookup"><span data-stu-id="ee01e-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="ee01e-166">El parámetro de método determinado se especifica mediante el nombre en lugar del tipo.</span><span class="sxs-lookup"><span data-stu-id="ee01e-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="ee01e-167">Debe haber presente al menos un atributo que represente un tipo de directiva, como `Activate` o `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ee01e-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee01e-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee01e-168">See also</span></span>

- [<span data-ttu-id="ee01e-169">Elemento \<Method></span><span class="sxs-lookup"><span data-stu-id="ee01e-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="ee01e-170">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ee01e-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ee01e-171">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ee01e-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="ee01e-172">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ee01e-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
