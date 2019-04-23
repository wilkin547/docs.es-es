---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116394"
---
# <a name="datacontractserializer"></a><span data-ttu-id="2f1d1-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2f1d1-101">\<dataContractSerializer></span></span>
<span data-ttu-id="2f1d1-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="2f1d1-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="2f1d1-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="2f1d1-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2f1d1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2f1d1-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2f1d1-106">\<behaviors></span></span>  
<span data-ttu-id="2f1d1-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2f1d1-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="2f1d1-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2f1d1-108">\<behavior></span></span>  
<span data-ttu-id="2f1d1-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2f1d1-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f1d1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f1d1-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f1d1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f1d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f1d1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f1d1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f1d1-113">Attributes</span></span>  
  
|<span data-ttu-id="2f1d1-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f1d1-114">Element</span></span>|<span data-ttu-id="2f1d1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f1d1-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f1d1-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="2f1d1-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="2f1d1-117">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="2f1d1-118">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="2f1d1-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="2f1d1-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="2f1d1-120">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="2f1d1-121">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f1d1-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f1d1-122">Child Elements</span></span>  
 <span data-ttu-id="2f1d1-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f1d1-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f1d1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2f1d1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f1d1-125">Element</span></span>|<span data-ttu-id="2f1d1-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f1d1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f1d1-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2f1d1-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="2f1d1-128">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="2f1d1-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2f1d1-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="2f1d1-130">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f1d1-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f1d1-131">Remarks</span></span>  
 <span data-ttu-id="2f1d1-132">Como se indicó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="2f1d1-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2f1d1-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="2f1d1-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2f1d1-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="2f1d1-135">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2f1d1-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1d1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f1d1-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="2f1d1-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="2f1d1-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="2f1d1-138">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="2f1d1-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
