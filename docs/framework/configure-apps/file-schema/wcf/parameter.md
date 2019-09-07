---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400112"
---
# <a name="parameter"></a><span data-ttu-id="75cf3-101">\<> de parámetros</span><span class="sxs-lookup"><span data-stu-id="75cf3-101">\<parameter></span></span>
<span data-ttu-id="75cf3-102">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="75cf3-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="75cf3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75cf3-104">&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="75cf3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="75cf3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="75cf3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="75cf3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> knownType**](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="75cf3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="75cf3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de parámetros**</span><span class="sxs-lookup"><span data-stu-id="75cf3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75cf3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75cf3-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75cf3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75cf3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="75cf3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75cf3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75cf3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="75cf3-113">Attributes</span></span>  
  
|<span data-ttu-id="75cf3-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="75cf3-114">Attribute</span></span>|<span data-ttu-id="75cf3-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75cf3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75cf3-116">index</span><span class="sxs-lookup"><span data-stu-id="75cf3-116">index</span></span>|<span data-ttu-id="75cf3-117">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="75cf3-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="75cf3-118">type</span><span class="sxs-lookup"><span data-stu-id="75cf3-118">type</span></span>|<span data-ttu-id="75cf3-119">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="75cf3-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="75cf3-120">Atributo index</span><span class="sxs-lookup"><span data-stu-id="75cf3-120">index Attribute</span></span>  
  
|<span data-ttu-id="75cf3-121">Valor</span><span class="sxs-lookup"><span data-stu-id="75cf3-121">Value</span></span>|<span data-ttu-id="75cf3-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75cf3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="75cf3-123">"0"</span><span class="sxs-lookup"><span data-stu-id="75cf3-123">"0"</span></span>|<span data-ttu-id="75cf3-124">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="75cf3-124">The first parameter in the generic type.</span></span> <span data-ttu-id="75cf3-125">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="75cf3-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="75cf3-126">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="75cf3-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="75cf3-127">"1"</span><span class="sxs-lookup"><span data-stu-id="75cf3-127">"1"</span></span>|<span data-ttu-id="75cf3-128">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="75cf3-128">The second parameter in a generic type.</span></span> <span data-ttu-id="75cf3-129">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="75cf3-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="75cf3-130">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="75cf3-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75cf3-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75cf3-131">Child Elements</span></span>  
 <span data-ttu-id="75cf3-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75cf3-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75cf3-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75cf3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="75cf3-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="75cf3-134">Element</span></span>|<span data-ttu-id="75cf3-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="75cf3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75cf3-136">\<knownType></span><span class="sxs-lookup"><span data-stu-id="75cf3-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="75cf3-137">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="75cf3-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75cf3-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75cf3-138">Remarks</span></span>  
 <span data-ttu-id="75cf3-139">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.</span><span class="sxs-lookup"><span data-stu-id="75cf3-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="75cf3-140">Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="75cf3-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="75cf3-141">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="75cf3-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="75cf3-142">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="75cf3-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75cf3-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="75cf3-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="75cf3-144">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="75cf3-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="75cf3-145">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="75cf3-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="75cf3-146">\<add></span><span class="sxs-lookup"><span data-stu-id="75cf3-146">\<add></span></span>](add-of-declaredtypes-element.md)
