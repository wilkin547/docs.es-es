---
description: 'Más información acerca de: <parameter>'
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: fb04cfb5bf451cdb99c23ae41ea8fafeb13f0d11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683819"
---
# \<parameter>

<span data-ttu-id="377f5-102">Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="377f5-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**  
  
## <a name="syntax"></a><span data-ttu-id="377f5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="377f5-103">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="377f5-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="377f5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="377f5-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="377f5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="377f5-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="377f5-106">Attributes</span></span>  
  
|<span data-ttu-id="377f5-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="377f5-107">Attribute</span></span>|<span data-ttu-id="377f5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="377f5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="377f5-109">índice</span><span class="sxs-lookup"><span data-stu-id="377f5-109">index</span></span>|<span data-ttu-id="377f5-110">Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.</span><span class="sxs-lookup"><span data-stu-id="377f5-110">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="377f5-111">type</span><span class="sxs-lookup"><span data-stu-id="377f5-111">type</span></span>|<span data-ttu-id="377f5-112">Una cadena que describe el tipo conocido usado para la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="377f5-112">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="377f5-113">Atributo index</span><span class="sxs-lookup"><span data-stu-id="377f5-113">index Attribute</span></span>  
  
|<span data-ttu-id="377f5-114">Value</span><span class="sxs-lookup"><span data-stu-id="377f5-114">Value</span></span>|<span data-ttu-id="377f5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="377f5-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="377f5-116">"0"</span><span class="sxs-lookup"><span data-stu-id="377f5-116">"0"</span></span>|<span data-ttu-id="377f5-117">El primer parámetro en el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="377f5-117">The first parameter in the generic type.</span></span> <span data-ttu-id="377f5-118">Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.</span><span class="sxs-lookup"><span data-stu-id="377f5-118">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="377f5-119">Si se usa como tipo declarado, el índice estaría establecido en "0".</span><span class="sxs-lookup"><span data-stu-id="377f5-119">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="377f5-120">"1"</span><span class="sxs-lookup"><span data-stu-id="377f5-120">"1"</span></span>|<span data-ttu-id="377f5-121">El segundo parámetro en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="377f5-121">The second parameter in a generic type.</span></span> <span data-ttu-id="377f5-122">Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="377f5-122">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="377f5-123">Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".</span><span class="sxs-lookup"><span data-stu-id="377f5-123">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="377f5-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="377f5-124">Child Elements</span></span>  

 <span data-ttu-id="377f5-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="377f5-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="377f5-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="377f5-126">Parent Elements</span></span>  
  
|<span data-ttu-id="377f5-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="377f5-127">Element</span></span>|<span data-ttu-id="377f5-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="377f5-128">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="377f5-129">Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.</span><span class="sxs-lookup"><span data-stu-id="377f5-129">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="377f5-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="377f5-130">Remarks</span></span>  

 <span data-ttu-id="377f5-131">Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="377f5-131">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="377f5-132">Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.</span><span class="sxs-lookup"><span data-stu-id="377f5-132">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="377f5-133">Este elemento de configuración no puede tener al mismo tiempo ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="377f5-133">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="377f5-134">Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="377f5-134">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377f5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="377f5-135">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="377f5-136">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="377f5-136">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
