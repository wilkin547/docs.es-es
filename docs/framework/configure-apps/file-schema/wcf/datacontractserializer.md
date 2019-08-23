---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8814a48df8933cf08db78e397c24d42f2da26026
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919231"
---
# <a name="datacontractserializer"></a><span data-ttu-id="3a15e-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3a15e-102">dataContractSerializer</span></span>
<span data-ttu-id="3a15e-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3a15e-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="3a15e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3a15e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a15e-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3a15e-105">\<behaviors></span></span>  
<span data-ttu-id="3a15e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3a15e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="3a15e-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3a15e-107">\<behavior></span></span>  
<span data-ttu-id="3a15e-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="3a15e-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a15e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a15e-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a15e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a15e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a15e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a15e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a15e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a15e-112">Attributes</span></span>  
  
|<span data-ttu-id="3a15e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a15e-113">Element</span></span>|<span data-ttu-id="3a15e-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3a15e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a15e-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="3a15e-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="3a15e-116">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="3a15e-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="3a15e-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="3a15e-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="3a15e-118">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="3a15e-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a15e-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a15e-119">Child Elements</span></span>  
 <span data-ttu-id="3a15e-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a15e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a15e-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a15e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3a15e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a15e-122">Element</span></span>|<span data-ttu-id="3a15e-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3a15e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a15e-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3a15e-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3a15e-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3a15e-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a15e-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a15e-126">Remarks</span></span>  
 <span data-ttu-id="3a15e-127">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3a15e-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3a15e-128">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a15e-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="3a15e-129">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="3a15e-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a15e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a15e-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="3a15e-131">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="3a15e-131">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="3a15e-132">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="3a15e-132">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
