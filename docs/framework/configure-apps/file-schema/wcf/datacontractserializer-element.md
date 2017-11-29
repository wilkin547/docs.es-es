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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ba6a70f6d618446ed3ffd446c06c8f3c88354ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="6e6f2-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="6e6f2-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="6e6f2-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="6e6f2-104">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="6e6f2-105">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="6e6f2-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="6e6f2-107">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-107">\<behaviors></span></span>  
<span data-ttu-id="6e6f2-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="6e6f2-109">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-109">\<behavior></span></span>  
<span data-ttu-id="6e6f2-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6f2-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e6f2-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e6f2-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6e6f2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6e6f2-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e6f2-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e6f2-114">Attributes</span></span>  
  
|<span data-ttu-id="6e6f2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e6f2-115">Element</span></span>|<span data-ttu-id="6e6f2-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e6f2-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6e6f2-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="6e6f2-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="6e6f2-118">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="6e6f2-119">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="6e6f2-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="6e6f2-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="6e6f2-121">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="6e6f2-122">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e6f2-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6e6f2-123">Child Elements</span></span>  
 <span data-ttu-id="6e6f2-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e6f2-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6e6f2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6e6f2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e6f2-126">Element</span></span>|<span data-ttu-id="6e6f2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e6f2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e6f2-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="6e6f2-129">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="6e6f2-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="6e6f2-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="6e6f2-131">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e6f2-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e6f2-132">Remarks</span></span>  
 <span data-ttu-id="6e6f2-133">Como se mencionó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="6e6f2-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="6e6f2-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="6e6f2-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6e6f2-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="6e6f2-136">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6e6f2-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6f2-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e6f2-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="6e6f2-138">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="6e6f2-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="6e6f2-139">Transferencia de datos y serialización</span><span class="sxs-lookup"><span data-stu-id="6e6f2-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
