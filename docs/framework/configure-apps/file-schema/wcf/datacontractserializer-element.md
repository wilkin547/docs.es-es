---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925913"
---
# <a name="datacontractserializer"></a><span data-ttu-id="5b9a9-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5b9a9-101">\<dataContractSerializer></span></span>
<span data-ttu-id="5b9a9-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="5b9a9-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="5b9a9-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="5b9a9-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b9a9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b9a9-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5b9a9-106">\<behaviors></span></span>  
<span data-ttu-id="5b9a9-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5b9a9-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="5b9a9-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5b9a9-108">\<behavior></span></span>  
<span data-ttu-id="5b9a9-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5b9a9-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b9a9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b9a9-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b9a9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b9a9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5b9a9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b9a9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b9a9-113">Attributes</span></span>  
  
|<span data-ttu-id="5b9a9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b9a9-114">Element</span></span>|<span data-ttu-id="5b9a9-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5b9a9-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b9a9-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="5b9a9-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="5b9a9-117">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="5b9a9-118">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="5b9a9-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="5b9a9-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="5b9a9-120">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="5b9a9-121">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b9a9-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b9a9-122">Child Elements</span></span>  
 <span data-ttu-id="5b9a9-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b9a9-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b9a9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5b9a9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b9a9-125">Element</span></span>|<span data-ttu-id="5b9a9-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5b9a9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b9a9-127">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5b9a9-127">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="5b9a9-128">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="5b9a9-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="5b9a9-129">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="5b9a9-130">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b9a9-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b9a9-131">Remarks</span></span>  
 <span data-ttu-id="5b9a9-132">Como se indica en la introducción de este tema, esta es la segunda jerarquía en la \<que se produce el elemento > de X509Extension.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="5b9a9-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="5b9a9-133">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="5b9a9-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="5b9a9-134">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="5b9a9-135">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5b9a9-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9a9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b9a9-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="5b9a9-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="5b9a9-137">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="5b9a9-138">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="5b9a9-138">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
