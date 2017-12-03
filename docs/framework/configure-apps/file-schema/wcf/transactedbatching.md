---
title: '&lt;transactedBatching&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d89b6f63f71d0ce5c3f757af7a1af347d875f333
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="43531-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="43531-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="43531-103">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="43531-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="43531-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="43531-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="43531-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="43531-105">\<behaviors></span></span>  
<span data-ttu-id="43531-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="43531-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="43531-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="43531-107">\<behavior></span></span>  
<span data-ttu-id="43531-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="43531-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43531-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43531-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43531-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43531-110">Attributes and Elements</span></span>  
 <span data-ttu-id="43531-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43531-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43531-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="43531-112">Attributes</span></span>  
  
|<span data-ttu-id="43531-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="43531-113">Attribute</span></span>|<span data-ttu-id="43531-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="43531-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="43531-115">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="43531-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="43531-116">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="43531-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43531-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43531-117">Child Elements</span></span>  
 <span data-ttu-id="43531-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43531-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43531-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43531-119">Parent Elements</span></span>  
  
|<span data-ttu-id="43531-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="43531-120">Element</span></span>|<span data-ttu-id="43531-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="43531-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43531-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="43531-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="43531-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="43531-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43531-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43531-124">Remarks</span></span>  
 <span data-ttu-id="43531-125">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="43531-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="43531-126">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="43531-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43531-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43531-127">Example</span></span>  
 <span data-ttu-id="43531-128">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="43531-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
        </baseAddresses>  
      </host>  
  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />  
  
      <!-- the mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="endpointBehavior">  
        <transactedBatching maxBatchSize="10" />  
      </behavior>  
    </endpointBehaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43531-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="43531-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
