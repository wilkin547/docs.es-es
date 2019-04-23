---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230803"
---
# <a name="parameter"></a><span data-ttu-id="5786e-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="5786e-101">\<parameter></span></span>
<span data-ttu-id="5786e-102">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5786e-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="5786e-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="5786e-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="5786e-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5786e-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="5786e-105">\<declaredTypes > elemento</span><span class="sxs-lookup"><span data-stu-id="5786e-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="5786e-106">\<Agregar > elemento para \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="5786e-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="5786e-107">\<knownType > elemento</span><span class="sxs-lookup"><span data-stu-id="5786e-107">\<knownType> Element</span></span>  
<span data-ttu-id="5786e-108">\<parámetro > elemento</span><span class="sxs-lookup"><span data-stu-id="5786e-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5786e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5786e-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5786e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5786e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5786e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5786e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5786e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5786e-112">Attributes</span></span>  
  
|<span data-ttu-id="5786e-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5786e-113">Attribute</span></span>|<span data-ttu-id="5786e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5786e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5786e-115">índice</span><span class="sxs-lookup"><span data-stu-id="5786e-115">index</span></span>|<span data-ttu-id="5786e-116">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="5786e-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="5786e-117">type</span><span class="sxs-lookup"><span data-stu-id="5786e-117">type</span></span>|<span data-ttu-id="5786e-118">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="5786e-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="5786e-119">Atributo index</span><span class="sxs-lookup"><span data-stu-id="5786e-119">index Attribute</span></span>  
  
|<span data-ttu-id="5786e-120">Valor</span><span class="sxs-lookup"><span data-stu-id="5786e-120">Value</span></span>|<span data-ttu-id="5786e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5786e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5786e-122">"0"</span><span class="sxs-lookup"><span data-stu-id="5786e-122">"0"</span></span>|<span data-ttu-id="5786e-123">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5786e-123">The first parameter in the generic type.</span></span> <span data-ttu-id="5786e-124">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="5786e-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="5786e-125">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="5786e-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="5786e-126">"1"</span><span class="sxs-lookup"><span data-stu-id="5786e-126">"1"</span></span>|<span data-ttu-id="5786e-127">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5786e-127">The second parameter in a generic type.</span></span> <span data-ttu-id="5786e-128">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="5786e-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="5786e-129">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="5786e-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5786e-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5786e-130">Child Elements</span></span>  
 <span data-ttu-id="5786e-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5786e-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5786e-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5786e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="5786e-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5786e-133">Element</span></span>|<span data-ttu-id="5786e-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="5786e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5786e-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="5786e-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="5786e-136">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="5786e-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5786e-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5786e-137">Remarks</span></span>  
 <span data-ttu-id="5786e-138">Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5786e-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="5786e-139">Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="5786e-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="5786e-140">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="5786e-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="5786e-141">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="5786e-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5786e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5786e-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="5786e-143">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="5786e-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="5786e-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5786e-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="5786e-145">\<add></span><span class="sxs-lookup"><span data-stu-id="5786e-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
