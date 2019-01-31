---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 1b4fd959d5e522150751d2e9b8be8c5b2252bf27
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254956"
---
# <a name="datacontractserializer"></a><span data-ttu-id="cfb55-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="cfb55-101">\<dataContractSerializer></span></span>
<span data-ttu-id="cfb55-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cfb55-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="cfb55-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="cfb55-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="cfb55-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="cfb55-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="cfb55-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cfb55-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="cfb55-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="cfb55-106">\<behaviors></span></span>  
<span data-ttu-id="cfb55-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cfb55-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="cfb55-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="cfb55-108">\<behavior></span></span>  
<span data-ttu-id="cfb55-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="cfb55-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb55-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfb55-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfb55-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cfb55-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cfb55-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cfb55-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfb55-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cfb55-113">Attributes</span></span>  
  
|<span data-ttu-id="cfb55-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfb55-114">Element</span></span>|<span data-ttu-id="cfb55-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfb55-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfb55-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="cfb55-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="cfb55-117">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="cfb55-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="cfb55-118">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="cfb55-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="cfb55-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="cfb55-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="cfb55-120">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="cfb55-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="cfb55-121">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="cfb55-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfb55-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cfb55-122">Child Elements</span></span>  
 <span data-ttu-id="cfb55-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cfb55-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfb55-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cfb55-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cfb55-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfb55-125">Element</span></span>|<span data-ttu-id="cfb55-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfb55-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfb55-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cfb55-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="cfb55-128">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="cfb55-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="cfb55-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="cfb55-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="cfb55-130">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cfb55-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfb55-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfb55-131">Remarks</span></span>  
 <span data-ttu-id="cfb55-132">Como se indicó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="cfb55-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="cfb55-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="cfb55-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="cfb55-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="cfb55-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="cfb55-135">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="cfb55-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb55-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfb55-136">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="cfb55-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="cfb55-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="cfb55-138">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="cfb55-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
