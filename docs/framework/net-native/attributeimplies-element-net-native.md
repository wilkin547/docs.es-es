---
description: 'Más información sobre: <AttributeImplies> elemento (.net Native)'
title: <AttributeImplies> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 5af1f60f2c1e556281f2f1d392b1a046e52dd277
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747912"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="269a9-103">\<AttributeImplies> Elemento (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="269a9-103">\<AttributeImplies> Element (.NET Native)</span></span>

<span data-ttu-id="269a9-104">Define la directiva para los elementos de código a los que se les aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="269a9-104">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="269a9-105">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="269a9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="269a9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="269a9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="269a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="269a9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="269a9-108">Attributes</span></span>  
  
|<span data-ttu-id="269a9-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="269a9-109">Attribute</span></span>|<span data-ttu-id="269a9-110">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="269a9-110">Attribute type</span></span>|<span data-ttu-id="269a9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="269a9-111">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="269a9-112">Reflexión</span><span class="sxs-lookup"><span data-stu-id="269a9-112">Reflection</span></span>|<span data-ttu-id="269a9-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-113">Optional attribute.</span></span> <span data-ttu-id="269a9-114">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="269a9-114">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="269a9-115">Reflexión</span><span class="sxs-lookup"><span data-stu-id="269a9-115">Reflection</span></span>|<span data-ttu-id="269a9-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-116">Optional attribute.</span></span> <span data-ttu-id="269a9-117">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="269a9-117">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="269a9-118">Reflexión</span><span class="sxs-lookup"><span data-stu-id="269a9-118">Reflection</span></span>|<span data-ttu-id="269a9-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-119">Optional attribute.</span></span> <span data-ttu-id="269a9-120">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="269a9-120">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="269a9-121">Serialización</span><span class="sxs-lookup"><span data-stu-id="269a9-121">Serialization</span></span>|<span data-ttu-id="269a9-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-122">Optional attribute.</span></span> <span data-ttu-id="269a9-123">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="269a9-123">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="269a9-124">Serialización</span><span class="sxs-lookup"><span data-stu-id="269a9-124">Serialization</span></span>|<span data-ttu-id="269a9-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-125">Optional attribute.</span></span> <span data-ttu-id="269a9-126">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="269a9-126">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="269a9-127">Serialización</span><span class="sxs-lookup"><span data-stu-id="269a9-127">Serialization</span></span>|<span data-ttu-id="269a9-128">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-128">Optional attribute.</span></span> <span data-ttu-id="269a9-129">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="269a9-129">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="269a9-130">Serialización</span><span class="sxs-lookup"><span data-stu-id="269a9-130">Serialization</span></span>|<span data-ttu-id="269a9-131">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-131">Optional attribute.</span></span> <span data-ttu-id="269a9-132">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="269a9-132">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="269a9-133">Interop</span><span class="sxs-lookup"><span data-stu-id="269a9-133">Interop</span></span>|<span data-ttu-id="269a9-134">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-134">Optional attribute.</span></span> <span data-ttu-id="269a9-135">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="269a9-135">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="269a9-136">Interop</span><span class="sxs-lookup"><span data-stu-id="269a9-136">Interop</span></span>|<span data-ttu-id="269a9-137">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-137">Optional attribute.</span></span> <span data-ttu-id="269a9-138">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="269a9-138">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="269a9-139">Interop</span><span class="sxs-lookup"><span data-stu-id="269a9-139">Interop</span></span>|<span data-ttu-id="269a9-140">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="269a9-140">Optional attribute.</span></span> <span data-ttu-id="269a9-141">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="269a9-141">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="269a9-142">Todos los atributos</span><span class="sxs-lookup"><span data-stu-id="269a9-142">All attributes</span></span>  
  
|<span data-ttu-id="269a9-143">Value</span><span class="sxs-lookup"><span data-stu-id="269a9-143">Value</span></span>|<span data-ttu-id="269a9-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="269a9-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="269a9-145">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="269a9-145">*policy_setting*</span></span>|<span data-ttu-id="269a9-146">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="269a9-146">The setting to apply to this policy type.</span></span> <span data-ttu-id="269a9-147">Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="269a9-147">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="269a9-148">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="269a9-148">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="269a9-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="269a9-149">Child Elements</span></span>  

 <span data-ttu-id="269a9-150">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="269a9-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="269a9-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="269a9-151">Parent Elements</span></span>  
  
|<span data-ttu-id="269a9-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="269a9-152">Element</span></span>|<span data-ttu-id="269a9-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="269a9-153">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="269a9-154">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="269a9-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="269a9-155">Observaciones</span><span class="sxs-lookup"><span data-stu-id="269a9-155">Remarks</span></span>  

 <span data-ttu-id="269a9-156">El elemento `<AttributeImplies>` se utiliza si su tipo contenedor es un atributo (es decir, una clase derivada de <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="269a9-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="269a9-157">Si el atributo se aplica a un determinado elemento del programa, la directiva definida por el elemento `<AttributeImplies>` se aplica a ese elemento del programa.</span><span class="sxs-lookup"><span data-stu-id="269a9-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="269a9-158">Todos los atributos de reflexión, serialización e interoperabilidad son opcionales, aunque al menos uno debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="269a9-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269a9-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="269a9-159">See also</span></span>

- [<span data-ttu-id="269a9-160">Elemento \<Type></span><span class="sxs-lookup"><span data-stu-id="269a9-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="269a9-161">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="269a9-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="269a9-162">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="269a9-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="269a9-163">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="269a9-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
