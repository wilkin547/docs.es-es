---
title: <AttributeImplies>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181064"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="2bc13-102">\<AttributeImplies> Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2bc13-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="2bc13-103">Define la directiva para los elementos de código a los que se les aplica el atributo.</span><span class="sxs-lookup"><span data-stu-id="2bc13-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc13-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bc13-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2bc13-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2bc13-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2bc13-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bc13-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2bc13-107">Attributes</span></span>  
  
|<span data-ttu-id="2bc13-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2bc13-108">Attribute</span></span>|<span data-ttu-id="2bc13-109">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="2bc13-109">Attribute type</span></span>|<span data-ttu-id="2bc13-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bc13-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="2bc13-111">Reflexión</span><span class="sxs-lookup"><span data-stu-id="2bc13-111">Reflection</span></span>|<span data-ttu-id="2bc13-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-112">Optional attribute.</span></span> <span data-ttu-id="2bc13-113">Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="2bc13-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="2bc13-114">Reflexión</span><span class="sxs-lookup"><span data-stu-id="2bc13-114">Reflection</span></span>|<span data-ttu-id="2bc13-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-115">Optional attribute.</span></span> <span data-ttu-id="2bc13-116">Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2bc13-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="2bc13-117">Reflexión</span><span class="sxs-lookup"><span data-stu-id="2bc13-117">Reflection</span></span>|<span data-ttu-id="2bc13-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-118">Optional attribute.</span></span> <span data-ttu-id="2bc13-119">Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.</span><span class="sxs-lookup"><span data-stu-id="2bc13-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="2bc13-120">Serialización</span><span class="sxs-lookup"><span data-stu-id="2bc13-120">Serialization</span></span>|<span data-ttu-id="2bc13-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-121">Optional attribute.</span></span> <span data-ttu-id="2bc13-122">Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="2bc13-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="2bc13-123">Serialización</span><span class="sxs-lookup"><span data-stu-id="2bc13-123">Serialization</span></span>|<span data-ttu-id="2bc13-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-124">Optional attribute.</span></span> <span data-ttu-id="2bc13-125">Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2bc13-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="2bc13-126">Serialización</span><span class="sxs-lookup"><span data-stu-id="2bc13-126">Serialization</span></span>|<span data-ttu-id="2bc13-127">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-127">Optional attribute.</span></span> <span data-ttu-id="2bc13-128">Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2bc13-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="2bc13-129">Serialización</span><span class="sxs-lookup"><span data-stu-id="2bc13-129">Serialization</span></span>|<span data-ttu-id="2bc13-130">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-130">Optional attribute.</span></span> <span data-ttu-id="2bc13-131">Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2bc13-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="2bc13-132">Interop</span><span class="sxs-lookup"><span data-stu-id="2bc13-132">Interop</span></span>|<span data-ttu-id="2bc13-133">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-133">Optional attribute.</span></span> <span data-ttu-id="2bc13-134">Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.</span><span class="sxs-lookup"><span data-stu-id="2bc13-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="2bc13-135">Interop</span><span class="sxs-lookup"><span data-stu-id="2bc13-135">Interop</span></span>|<span data-ttu-id="2bc13-136">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-136">Optional attribute.</span></span> <span data-ttu-id="2bc13-137">Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.</span><span class="sxs-lookup"><span data-stu-id="2bc13-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="2bc13-138">Interop</span><span class="sxs-lookup"><span data-stu-id="2bc13-138">Interop</span></span>|<span data-ttu-id="2bc13-139">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2bc13-139">Optional attribute.</span></span> <span data-ttu-id="2bc13-140">Controla la directiva de cálculo de referencias de tipos de valor a código nativo.</span><span class="sxs-lookup"><span data-stu-id="2bc13-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="2bc13-141">Todos los atributos</span><span class="sxs-lookup"><span data-stu-id="2bc13-141">All attributes</span></span>  
  
|<span data-ttu-id="2bc13-142">Value</span><span class="sxs-lookup"><span data-stu-id="2bc13-142">Value</span></span>|<span data-ttu-id="2bc13-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bc13-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2bc13-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2bc13-144">*policy_setting*</span></span>|<span data-ttu-id="2bc13-145">Configuración que se va a aplicar a este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="2bc13-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="2bc13-146">Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`.</span><span class="sxs-lookup"><span data-stu-id="2bc13-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="2bc13-147">Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="2bc13-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bc13-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2bc13-148">Child Elements</span></span>  
 <span data-ttu-id="2bc13-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2bc13-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2bc13-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2bc13-150">Parent Elements</span></span>  
  
|<span data-ttu-id="2bc13-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="2bc13-151">Element</span></span>|<span data-ttu-id="2bc13-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bc13-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bc13-153">\<Tipo></span><span class="sxs-lookup"><span data-stu-id="2bc13-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="2bc13-154">Aplica la directiva de reflexión a un tipo y a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="2bc13-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bc13-155">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2bc13-155">Remarks</span></span>  
 <span data-ttu-id="2bc13-156">El elemento `<AttributeImplies>` se utiliza si su tipo contenedor es un atributo (es decir, una clase derivada de <xref:System.Attribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="2bc13-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="2bc13-157">Si el atributo se aplica a un determinado elemento del programa, la directiva definida por el elemento `<AttributeImplies>` se aplica a ese elemento del programa.</span><span class="sxs-lookup"><span data-stu-id="2bc13-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="2bc13-158">Todos los atributos de reflexión, serialización e interoperabilidad son opcionales, aunque al menos uno debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="2bc13-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc13-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bc13-159">See also</span></span>

- [<span data-ttu-id="2bc13-160">\<Elemento de> de tipo</span><span class="sxs-lookup"><span data-stu-id="2bc13-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="2bc13-161">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="2bc13-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2bc13-162">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2bc13-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="2bc13-163">Configuración de directiva de la directiva en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="2bc13-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
