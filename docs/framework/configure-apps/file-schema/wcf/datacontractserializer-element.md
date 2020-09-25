---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 2a994a8ba97d4c65fdaba5a85e779dd9935e3074
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195042"
---
# \<dataContractSerializer>

<span data-ttu-id="39c45-101">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="39c45-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="39c45-102">Este elemento se produce en dos jerarquías diferentes.</span><span class="sxs-lookup"><span data-stu-id="39c45-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="39c45-103">Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="39c45-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="39c45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39c45-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39c45-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="39c45-105">Attributes and Elements</span></span>  

 <span data-ttu-id="39c45-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="39c45-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39c45-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="39c45-107">Attributes</span></span>  
  
|<span data-ttu-id="39c45-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="39c45-108">Element</span></span>|<span data-ttu-id="39c45-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="39c45-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39c45-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="39c45-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="39c45-111">Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="39c45-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="39c45-112">Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.</span><span class="sxs-lookup"><span data-stu-id="39c45-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="39c45-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="39c45-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="39c45-114">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="39c45-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="39c45-115">Este atributo es 65536.</span><span class="sxs-lookup"><span data-stu-id="39c45-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39c45-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="39c45-116">Child Elements</span></span>  

 <span data-ttu-id="39c45-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="39c45-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39c45-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="39c45-118">Parent Elements</span></span>  
  
|<span data-ttu-id="39c45-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="39c45-119">Element</span></span>|<span data-ttu-id="39c45-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="39c45-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="39c45-121">Una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="39c45-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="39c45-122">Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="39c45-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c45-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39c45-123">Remarks</span></span>  

 <span data-ttu-id="39c45-124">Como se indica en la introducción de este tema, esta es la segunda jerarquía en la que \<X509Extension> se produce el elemento.</span><span class="sxs-lookup"><span data-stu-id="39c45-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="39c45-125">Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="39c45-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c45-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39c45-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="39c45-127">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="39c45-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="39c45-128">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="39c45-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
