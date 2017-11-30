---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4044e81b7c33c7a755678e79586dd4f37cf54ed5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="f70c7-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="f70c7-102">dataContractSerializer</span></span>
<span data-ttu-id="f70c7-103">Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f70c7-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="f70c7-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f70c7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f70c7-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f70c7-105">\<behaviors></span></span>  
<span data-ttu-id="f70c7-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f70c7-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f70c7-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f70c7-107">\<behavior></span></span>  
<span data-ttu-id="f70c7-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="f70c7-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f70c7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f70c7-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f70c7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f70c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f70c7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f70c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f70c7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f70c7-112">Attributes</span></span>  
  
|<span data-ttu-id="f70c7-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f70c7-113">Element</span></span>|<span data-ttu-id="f70c7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f70c7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f70c7-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="f70c7-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="f70c7-116">Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.</span><span class="sxs-lookup"><span data-stu-id="f70c7-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="f70c7-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="f70c7-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="f70c7-118">Un entero que especifica el número máximo de elementos para serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="f70c7-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f70c7-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f70c7-119">Child Elements</span></span>  
 <span data-ttu-id="f70c7-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f70c7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f70c7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f70c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f70c7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f70c7-122">Element</span></span>|<span data-ttu-id="f70c7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f70c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f70c7-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f70c7-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f70c7-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f70c7-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f70c7-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f70c7-126">Remarks</span></span>  
 <span data-ttu-id="f70c7-127">Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="f70c7-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f70c7-128">El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f70c7-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="f70c7-129">En caso contrario, el comportamiento resultante no está definido.</span><span class="sxs-lookup"><span data-stu-id="f70c7-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70c7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f70c7-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="f70c7-131">Los tipos conocidos de contrato de datos</span><span class="sxs-lookup"><span data-stu-id="f70c7-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="f70c7-132">Transferencia de datos y serialización</span><span class="sxs-lookup"><span data-stu-id="f70c7-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
