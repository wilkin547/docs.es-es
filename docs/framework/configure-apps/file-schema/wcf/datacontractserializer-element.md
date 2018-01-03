---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="740dc-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="740dc-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="740dc-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="740dc-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="740dc-104">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="740dc-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="740dc-105">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="740dc-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="740dc-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="740dc-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="740dc-107">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="740dc-107">\<behaviors></span></span>  
<span data-ttu-id="740dc-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="740dc-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="740dc-109">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="740dc-109">\<behavior></span></span>  
<span data-ttu-id="740dc-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="740dc-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="740dc-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="740dc-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="740dc-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="740dc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="740dc-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="740dc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="740dc-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="740dc-114">Attributes</span></span>  
  
|<span data-ttu-id="740dc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="740dc-115">Element</span></span>|<span data-ttu-id="740dc-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="740dc-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="740dc-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="740dc-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="740dc-118">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="740dc-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="740dc-119">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="740dc-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="740dc-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="740dc-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="740dc-121">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="740dc-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="740dc-122">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="740dc-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="740dc-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="740dc-123">Child Elements</span></span>  
 <span data-ttu-id="740dc-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="740dc-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="740dc-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="740dc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="740dc-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="740dc-126">Element</span></span>|<span data-ttu-id="740dc-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="740dc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="740dc-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="740dc-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="740dc-129">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="740dc-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="740dc-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="740dc-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="740dc-131">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="740dc-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="740dc-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="740dc-132">Remarks</span></span>  
 <span data-ttu-id="740dc-133">Como se mencionó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="740dc-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="740dc-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="740dc-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="740dc-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="740dc-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="740dc-136">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="740dc-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740dc-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="740dc-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="740dc-138">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="740dc-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="740dc-139">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="740dc-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
