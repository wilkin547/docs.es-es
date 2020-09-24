---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0e4cbc50c25d4fa1f67f283f2b52d4b174428cd3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153929"
---
# <a name="datacontractserializer"></a><span data-ttu-id="76c79-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="76c79-102">dataContractSerializer</span></span>

<span data-ttu-id="76c79-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="76c79-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="76c79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76c79-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76c79-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76c79-105">Attributes and Elements</span></span>  

 <span data-ttu-id="76c79-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76c79-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76c79-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="76c79-107">Attributes</span></span>  
  
|<span data-ttu-id="76c79-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="76c79-108">Element</span></span>|<span data-ttu-id="76c79-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="76c79-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76c79-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="76c79-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="76c79-111">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="76c79-111">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="76c79-112">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="76c79-112">maxItemsInObjectGraph</span></span>|<span data-ttu-id="76c79-113">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="76c79-113">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76c79-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76c79-114">Child Elements</span></span>  

 <span data-ttu-id="76c79-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76c79-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76c79-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76c79-116">Parent Elements</span></span>  
  
|<span data-ttu-id="76c79-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="76c79-117">Element</span></span>|<span data-ttu-id="76c79-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="76c79-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="76c79-119">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76c79-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76c79-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76c79-120">Remarks</span></span>  

 <span data-ttu-id="76c79-121">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="76c79-121">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="76c79-122">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="76c79-122">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="76c79-123">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="76c79-123">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76c79-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="76c79-124">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="76c79-125">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="76c79-125">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="76c79-126">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="76c79-126">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
