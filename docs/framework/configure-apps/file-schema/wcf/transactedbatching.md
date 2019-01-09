---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: f56751ea3f8bdc9ecbeff57db835e5fc2edbb73e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148453"
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="8c31a-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="8c31a-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="8c31a-103">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="8c31a-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="8c31a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c31a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c31a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="8c31a-105">\<behaviors></span></span>  
<span data-ttu-id="8c31a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8c31a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8c31a-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8c31a-107">\<behavior></span></span>  
<span data-ttu-id="8c31a-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="8c31a-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c31a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c31a-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c31a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8c31a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c31a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8c31a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c31a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c31a-112">Attributes</span></span>  
  
|<span data-ttu-id="8c31a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8c31a-113">Attribute</span></span>|<span data-ttu-id="8c31a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c31a-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="8c31a-115">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="8c31a-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="8c31a-116">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="8c31a-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c31a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8c31a-117">Child Elements</span></span>  
 <span data-ttu-id="8c31a-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c31a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c31a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8c31a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8c31a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c31a-120">Element</span></span>|<span data-ttu-id="8c31a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c31a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c31a-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8c31a-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8c31a-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8c31a-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c31a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c31a-124">Remarks</span></span>  
 <span data-ttu-id="8c31a-125">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="8c31a-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="8c31a-126">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="8c31a-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c31a-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c31a-127">Example</span></span>  
 <span data-ttu-id="8c31a-128">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8c31a-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
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
  
## <a name="see-also"></a><span data-ttu-id="8c31a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c31a-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
