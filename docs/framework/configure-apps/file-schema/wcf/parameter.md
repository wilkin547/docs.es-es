---
title: '&lt;Parámetro&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 82a2f5c46c698508695fe5f13f67059860a50713
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148297"
---
# <a name="ltparametergt"></a><span data-ttu-id="68635-102">&lt;Parámetro&gt;</span><span class="sxs-lookup"><span data-stu-id="68635-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="68635-103">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="68635-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="68635-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="68635-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="68635-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="68635-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="68635-106">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="68635-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="68635-107">\<Agregar > elemento para \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="68635-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="68635-108">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="68635-108">\<knownType> Element</span></span>  
<span data-ttu-id="68635-109">\<parámetro > elemento</span><span class="sxs-lookup"><span data-stu-id="68635-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68635-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68635-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68635-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68635-111">Attributes and Elements</span></span>  
 <span data-ttu-id="68635-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68635-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68635-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="68635-113">Attributes</span></span>  
  
|<span data-ttu-id="68635-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="68635-114">Attribute</span></span>|<span data-ttu-id="68635-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="68635-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68635-116">índice</span><span class="sxs-lookup"><span data-stu-id="68635-116">index</span></span>|<span data-ttu-id="68635-117">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="68635-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="68635-118">tipo</span><span class="sxs-lookup"><span data-stu-id="68635-118">type</span></span>|<span data-ttu-id="68635-119">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="68635-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="68635-120">Atributo index</span><span class="sxs-lookup"><span data-stu-id="68635-120">index Attribute</span></span>  
  
|<span data-ttu-id="68635-121">Valor</span><span class="sxs-lookup"><span data-stu-id="68635-121">Value</span></span>|<span data-ttu-id="68635-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="68635-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68635-123">"0"</span><span class="sxs-lookup"><span data-stu-id="68635-123">"0"</span></span>|<span data-ttu-id="68635-124">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="68635-124">The first parameter in the generic type.</span></span> <span data-ttu-id="68635-125">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="68635-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="68635-126">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="68635-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="68635-127">"1"</span><span class="sxs-lookup"><span data-stu-id="68635-127">"1"</span></span>|<span data-ttu-id="68635-128">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="68635-128">The second parameter in a generic type.</span></span> <span data-ttu-id="68635-129">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="68635-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="68635-130">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="68635-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68635-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68635-131">Child Elements</span></span>  
 <span data-ttu-id="68635-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68635-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68635-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68635-133">Parent Elements</span></span>  
  
|<span data-ttu-id="68635-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="68635-134">Element</span></span>|<span data-ttu-id="68635-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="68635-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68635-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="68635-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="68635-137">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="68635-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68635-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68635-138">Remarks</span></span>  
 <span data-ttu-id="68635-139">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="68635-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="68635-140">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="68635-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="68635-141">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="68635-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="68635-142">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="68635-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68635-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="68635-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="68635-144">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="68635-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="68635-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="68635-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="68635-146">\<add></span><span class="sxs-lookup"><span data-stu-id="68635-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
