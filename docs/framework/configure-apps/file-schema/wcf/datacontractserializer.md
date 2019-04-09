---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 8ba16d9cc30b07d3e6b0924e6013ec01443867d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139053"
---
# <a name="datacontractserializer"></a><span data-ttu-id="c0c1a-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="c0c1a-102">dataContractSerializer</span></span>
<span data-ttu-id="c0c1a-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="c0c1a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c0c1a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c0c1a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c0c1a-105">\<behaviors></span></span>  
<span data-ttu-id="c0c1a-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c0c1a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c0c1a-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c0c1a-107">\<behavior></span></span>  
<span data-ttu-id="c0c1a-108">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="c0c1a-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c1a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0c1a-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0c1a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c0c1a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0c1a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0c1a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0c1a-112">Attributes</span></span>  
  
|<span data-ttu-id="c0c1a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0c1a-113">Element</span></span>|<span data-ttu-id="c0c1a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0c1a-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0c1a-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c0c1a-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="c0c1a-116">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="c0c1a-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c0c1a-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="c0c1a-118">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0c1a-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c0c1a-119">Child Elements</span></span>  
 <span data-ttu-id="c0c1a-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0c1a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c0c1a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c0c1a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0c1a-122">Element</span></span>|<span data-ttu-id="c0c1a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0c1a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0c1a-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c0c1a-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c0c1a-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0c1a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0c1a-126">Remarks</span></span>  
 <span data-ttu-id="c0c1a-127">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c0c1a-128">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="c0c1a-129">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="c0c1a-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c1a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c1a-130">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="c0c1a-131">Tipos conocidos de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="c0c1a-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="c0c1a-132">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="c0c1a-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
