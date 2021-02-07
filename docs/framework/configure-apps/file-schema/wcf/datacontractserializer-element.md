---
description: 'Más información acerca de: <dataContractSerializer>'
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 0705a40f55d76ef46a7debcd4ecfb5235c7c0d21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754438"
---
# \<dataContractSerializer>

<span data-ttu-id="d80a1-102">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d80a1-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="d80a1-103">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="d80a1-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="d80a1-104">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="d80a1-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="d80a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d80a1-105">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d80a1-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d80a1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d80a1-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d80a1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d80a1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d80a1-108">Attributes</span></span>  
  
|<span data-ttu-id="d80a1-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="d80a1-109">Element</span></span>|<span data-ttu-id="d80a1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d80a1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d80a1-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d80a1-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="d80a1-112">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="d80a1-112">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="d80a1-113">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="d80a1-113">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="d80a1-114">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d80a1-114">maxItemsInObjectGraph</span></span>|<span data-ttu-id="d80a1-115">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="d80a1-115">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="d80a1-116">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="d80a1-116">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d80a1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d80a1-117">Child Elements</span></span>  

 <span data-ttu-id="d80a1-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d80a1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d80a1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d80a1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d80a1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d80a1-120">Element</span></span>|<span data-ttu-id="d80a1-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d80a1-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="d80a1-122">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="d80a1-122">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="d80a1-123">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d80a1-123">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d80a1-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d80a1-124">Remarks</span></span>  

 <span data-ttu-id="d80a1-125">Como se indica en la introducción de este tema, esta es la segunda jerarquía en la que \<X509Extension> se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="d80a1-125">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="d80a1-126">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d80a1-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80a1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d80a1-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="d80a1-128">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="d80a1-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="d80a1-129">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="d80a1-129">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
