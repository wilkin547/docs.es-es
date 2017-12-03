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
ms.openlocfilehash: d38e3786c595c3fe6cc9ea54b68784c927901731
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="7e397-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="7e397-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="7e397-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7e397-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="7e397-104">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="7e397-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="7e397-105">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="7e397-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="7e397-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7e397-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="7e397-107">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="7e397-107">\<behaviors></span></span>  
<span data-ttu-id="7e397-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7e397-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="7e397-109">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7e397-109">\<behavior></span></span>  
<span data-ttu-id="7e397-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="7e397-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e397-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e397-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e397-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7e397-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7e397-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7e397-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e397-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7e397-114">Attributes</span></span>  
  
|<span data-ttu-id="7e397-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e397-115">Element</span></span>|<span data-ttu-id="7e397-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e397-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e397-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="7e397-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="7e397-118">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="7e397-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="7e397-119">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="7e397-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="7e397-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="7e397-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="7e397-121">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="7e397-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="7e397-122">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="7e397-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e397-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7e397-123">Child Elements</span></span>  
 <span data-ttu-id="7e397-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7e397-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e397-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7e397-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7e397-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e397-126">Element</span></span>|<span data-ttu-id="7e397-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e397-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e397-128">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7e397-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="7e397-129">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="7e397-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="7e397-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7e397-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="7e397-131">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7e397-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e397-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e397-132">Remarks</span></span>  
 <span data-ttu-id="7e397-133">Como se mencionó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="7e397-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="7e397-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="7e397-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="7e397-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="7e397-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="7e397-136">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7e397-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e397-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e397-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="7e397-138">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="7e397-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="7e397-139">Transferencia de datos y serialización</span><span class="sxs-lookup"><span data-stu-id="7e397-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
