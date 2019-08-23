---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: c3f2179835ad1232e115cad0decdd3d41bbdc160
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932846"
---
# <a name="parameter"></a><span data-ttu-id="b9771-101">\<> de parámetros</span><span class="sxs-lookup"><span data-stu-id="b9771-101">\<parameter></span></span>
<span data-ttu-id="b9771-102">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="b9771-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="b9771-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b9771-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="b9771-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b9771-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="b9771-105">\<declaredTypes >, elemento</span><span class="sxs-lookup"><span data-stu-id="b9771-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="b9771-106">\<Agregar > elemento para \<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b9771-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="b9771-107">\<knownType >, elemento</span><span class="sxs-lookup"><span data-stu-id="b9771-107">\<knownType> Element</span></span>  
<span data-ttu-id="b9771-108">\<parámetro > elemento</span><span class="sxs-lookup"><span data-stu-id="b9771-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9771-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9771-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9771-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b9771-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9771-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b9771-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9771-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b9771-112">Attributes</span></span>  
  
|<span data-ttu-id="b9771-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b9771-113">Attribute</span></span>|<span data-ttu-id="b9771-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b9771-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9771-115">index</span><span class="sxs-lookup"><span data-stu-id="b9771-115">index</span></span>|<span data-ttu-id="b9771-116">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="b9771-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="b9771-117">type</span><span class="sxs-lookup"><span data-stu-id="b9771-117">type</span></span>|<span data-ttu-id="b9771-118">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="b9771-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="b9771-119">Atributo index</span><span class="sxs-lookup"><span data-stu-id="b9771-119">index Attribute</span></span>  
  
|<span data-ttu-id="b9771-120">Value</span><span class="sxs-lookup"><span data-stu-id="b9771-120">Value</span></span>|<span data-ttu-id="b9771-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b9771-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b9771-122">"0"</span><span class="sxs-lookup"><span data-stu-id="b9771-122">"0"</span></span>|<span data-ttu-id="b9771-123">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="b9771-123">The first parameter in the generic type.</span></span> <span data-ttu-id="b9771-124">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b9771-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="b9771-125">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="b9771-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="b9771-126">"1"</span><span class="sxs-lookup"><span data-stu-id="b9771-126">"1"</span></span>|<span data-ttu-id="b9771-127">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="b9771-127">The second parameter in a generic type.</span></span> <span data-ttu-id="b9771-128">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="b9771-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="b9771-129">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="b9771-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9771-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b9771-130">Child Elements</span></span>  
 <span data-ttu-id="b9771-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b9771-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9771-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b9771-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b9771-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9771-133">Element</span></span>|<span data-ttu-id="b9771-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b9771-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9771-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="b9771-135">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="b9771-136">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="b9771-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9771-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9771-137">Remarks</span></span>  
 <span data-ttu-id="b9771-138">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="b9771-138">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b9771-139">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="b9771-139">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="b9771-140">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="b9771-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="b9771-141">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="b9771-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9771-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9771-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="b9771-143">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="b9771-143">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="b9771-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b9771-144">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="b9771-145">\<add></span><span class="sxs-lookup"><span data-stu-id="b9771-145">\<add></span></span>](add-of-declaredtypes-element.md)
