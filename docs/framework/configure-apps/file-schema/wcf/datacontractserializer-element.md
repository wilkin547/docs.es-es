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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704146"
---
# <a name="datacontractserializer"></a><span data-ttu-id="630ed-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="630ed-101">\<dataContractSerializer></span></span>
<span data-ttu-id="630ed-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="630ed-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="630ed-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="630ed-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="630ed-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="630ed-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="630ed-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="630ed-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="630ed-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="630ed-106">\<behaviors></span></span>  
<span data-ttu-id="630ed-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="630ed-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="630ed-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="630ed-108">\<behavior></span></span>  
<span data-ttu-id="630ed-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="630ed-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630ed-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="630ed-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="630ed-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="630ed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="630ed-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="630ed-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="630ed-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="630ed-113">Attributes</span></span>  
  
|<span data-ttu-id="630ed-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="630ed-114">Element</span></span>|<span data-ttu-id="630ed-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="630ed-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="630ed-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="630ed-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="630ed-117">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="630ed-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="630ed-118">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="630ed-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="630ed-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="630ed-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="630ed-120">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="630ed-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="630ed-121">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="630ed-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="630ed-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="630ed-122">Child Elements</span></span>  
 <span data-ttu-id="630ed-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="630ed-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="630ed-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="630ed-124">Parent Elements</span></span>  
  
|<span data-ttu-id="630ed-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="630ed-125">Element</span></span>|<span data-ttu-id="630ed-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="630ed-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="630ed-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="630ed-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="630ed-128">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="630ed-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="630ed-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="630ed-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="630ed-130">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="630ed-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="630ed-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="630ed-131">Remarks</span></span>  
 <span data-ttu-id="630ed-132">Como se indicó en la introducción de este tema, se trata de la segunda jerarquía en la que el \<X509Extension > se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="630ed-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="630ed-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="630ed-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="630ed-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="630ed-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="630ed-135">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="630ed-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630ed-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="630ed-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="630ed-137">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="630ed-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="630ed-138">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="630ed-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
