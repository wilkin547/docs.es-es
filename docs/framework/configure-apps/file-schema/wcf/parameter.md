---
title: "&lt;parámetro&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9db1921e2a6ee1ae2780f744c45fdb25efbf797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="0b96d-102">&lt;parámetro&gt;</span><span class="sxs-lookup"><span data-stu-id="0b96d-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="0b96d-103">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0b96d-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="0b96d-104">\<System.Runtime.Serialization ></span><span class="sxs-lookup"><span data-stu-id="0b96d-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="0b96d-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0b96d-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="0b96d-106">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="0b96d-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="0b96d-107">\<Agregar > (elemento) para \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="0b96d-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="0b96d-108">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="0b96d-108">\<knownType> Element</span></span>  
<span data-ttu-id="0b96d-109">\<parámetro > elemento</span><span class="sxs-lookup"><span data-stu-id="0b96d-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b96d-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b96d-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b96d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0b96d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0b96d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0b96d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b96d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b96d-113">Attributes</span></span>  
  
|<span data-ttu-id="0b96d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0b96d-114">Attribute</span></span>|<span data-ttu-id="0b96d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b96d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b96d-116">índice</span><span class="sxs-lookup"><span data-stu-id="0b96d-116">index</span></span>|<span data-ttu-id="0b96d-117">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="0b96d-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="0b96d-118">tipo</span><span class="sxs-lookup"><span data-stu-id="0b96d-118">type</span></span>|<span data-ttu-id="0b96d-119">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="0b96d-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="0b96d-120">Atributo index</span><span class="sxs-lookup"><span data-stu-id="0b96d-120">index Attribute</span></span>  
  
|<span data-ttu-id="0b96d-121">Valor</span><span class="sxs-lookup"><span data-stu-id="0b96d-121">Value</span></span>|<span data-ttu-id="0b96d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b96d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b96d-123">"0"</span><span class="sxs-lookup"><span data-stu-id="0b96d-123">"0"</span></span>|<span data-ttu-id="0b96d-124">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0b96d-124">The first parameter in the generic type.</span></span> <span data-ttu-id="0b96d-125">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="0b96d-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="0b96d-126">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="0b96d-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="0b96d-127">"1"</span><span class="sxs-lookup"><span data-stu-id="0b96d-127">"1"</span></span>|<span data-ttu-id="0b96d-128">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0b96d-128">The second parameter in a generic type.</span></span> <span data-ttu-id="0b96d-129">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="0b96d-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="0b96d-130">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="0b96d-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b96d-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0b96d-131">Child Elements</span></span>  
 <span data-ttu-id="0b96d-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b96d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b96d-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0b96d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="0b96d-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b96d-134">Element</span></span>|<span data-ttu-id="0b96d-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b96d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b96d-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="0b96d-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="0b96d-137">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="0b96d-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b96d-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b96d-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="0b96d-139">los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0b96d-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="0b96d-140">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="0b96d-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="0b96d-141">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="0b96d-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="0b96d-142">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="0b96d-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b96d-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b96d-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="0b96d-144">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="0b96d-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="0b96d-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="0b96d-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="0b96d-146">\<add></span><span class="sxs-lookup"><span data-stu-id="0b96d-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
