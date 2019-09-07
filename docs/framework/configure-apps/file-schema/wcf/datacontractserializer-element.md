---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400449"
---
# <a name="datacontractserializer"></a><span data-ttu-id="25d97-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="25d97-101">\<dataContractSerializer></span></span>
<span data-ttu-id="25d97-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="25d97-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="25d97-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="25d97-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="25d97-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="25d97-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="25d97-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25d97-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25d97-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="25d97-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25d97-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="25d97-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="25d97-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="25d97-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="25d97-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="25d97-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="25d97-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dataContractSerializer**</span><span class="sxs-lookup"><span data-stu-id="25d97-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d97-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25d97-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25d97-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="25d97-112">Attributes and Elements</span></span>  
 <span data-ttu-id="25d97-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="25d97-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25d97-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="25d97-114">Attributes</span></span>  
  
|<span data-ttu-id="25d97-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="25d97-115">Element</span></span>|<span data-ttu-id="25d97-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25d97-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25d97-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="25d97-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="25d97-118">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="25d97-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="25d97-119">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="25d97-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="25d97-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="25d97-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="25d97-121">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="25d97-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="25d97-122">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="25d97-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25d97-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="25d97-123">Child Elements</span></span>  
 <span data-ttu-id="25d97-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="25d97-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25d97-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="25d97-125">Parent Elements</span></span>  
  
|<span data-ttu-id="25d97-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="25d97-126">Element</span></span>|<span data-ttu-id="25d97-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25d97-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25d97-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="25d97-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="25d97-129">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="25d97-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="25d97-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="25d97-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="25d97-131">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="25d97-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25d97-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25d97-132">Remarks</span></span>  
 <span data-ttu-id="25d97-133">Como se indica en la introducción de este tema, esta es la segunda jerarquía en la \<que se produce el elemento > de X509Extension.</span><span class="sxs-lookup"><span data-stu-id="25d97-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="25d97-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="25d97-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="25d97-135">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="25d97-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="25d97-136">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="25d97-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d97-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="25d97-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="25d97-138">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="25d97-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="25d97-139">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="25d97-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
