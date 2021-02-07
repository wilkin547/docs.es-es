---
description: 'Más información sobre: dataContractSerializer'
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 5dee59ba97a1632c142179aee79058dd3ce8c349
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754412"
---
# <a name="datacontractserializer"></a><span data-ttu-id="88c59-103">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="88c59-103">dataContractSerializer</span></span>

<span data-ttu-id="88c59-104">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="88c59-104">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="88c59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88c59-105">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88c59-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88c59-106">Attributes and Elements</span></span>  

 <span data-ttu-id="88c59-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88c59-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88c59-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="88c59-108">Attributes</span></span>  
  
|<span data-ttu-id="88c59-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="88c59-109">Element</span></span>|<span data-ttu-id="88c59-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="88c59-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88c59-111">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="88c59-111">ignoreExtensionDataObject</span></span>|<span data-ttu-id="88c59-112">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="88c59-112">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="88c59-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="88c59-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="88c59-114">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="88c59-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88c59-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88c59-115">Child Elements</span></span>  

 <span data-ttu-id="88c59-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="88c59-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88c59-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88c59-117">Parent Elements</span></span>  
  
|<span data-ttu-id="88c59-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="88c59-118">Element</span></span>|<span data-ttu-id="88c59-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="88c59-119">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="88c59-120">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="88c59-120">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88c59-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88c59-121">Remarks</span></span>  

 <span data-ttu-id="88c59-122">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="88c59-122">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="88c59-123">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="88c59-123">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="88c59-124">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="88c59-124">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c59-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="88c59-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="88c59-126">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="88c59-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="88c59-127">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="88c59-127">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
