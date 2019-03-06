---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 43415d9eac5e61f42006aecb3248dec9811eb3e6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366466"
---
# <a name="transactedbatching"></a><span data-ttu-id="e746f-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="e746f-101">\<transactedBatching></span></span>

<span data-ttu-id="e746f-102">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e746f-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="e746f-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="e746f-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="e746f-104">\<comportamientos > \\</span><span class="sxs-lookup"><span data-stu-id="e746f-104">\<behaviors>\\</span></span>
<span data-ttu-id="e746f-105">\<endpointBehaviors>\\</span><span class="sxs-lookup"><span data-stu-id="e746f-105">\<endpointBehaviors>\\</span></span>
<span data-ttu-id="e746f-106">\<comportamiento > \\</span><span class="sxs-lookup"><span data-stu-id="e746f-106">\<behavior>\\</span></span>
<span data-ttu-id="e746f-107">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="e746f-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="e746f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e746f-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e746f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e746f-109">Attributes and Elements</span></span>

<span data-ttu-id="e746f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e746f-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e746f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e746f-111">Attributes</span></span>

|<span data-ttu-id="e746f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e746f-112">Attribute</span></span>|<span data-ttu-id="e746f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e746f-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="e746f-114">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="e746f-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="e746f-115">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="e746f-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e746f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e746f-116">Child Elements</span></span>

<span data-ttu-id="e746f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e746f-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e746f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e746f-118">Parent Elements</span></span>

|<span data-ttu-id="e746f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e746f-119">Element</span></span>|<span data-ttu-id="e746f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e746f-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e746f-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e746f-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e746f-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e746f-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e746f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e746f-123">Remarks</span></span>

<span data-ttu-id="e746f-124">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="e746f-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="e746f-125">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e746f-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="e746f-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e746f-126">Example</span></span>

<span data-ttu-id="e746f-127">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e746f-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
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

## <a name="see-also"></a><span data-ttu-id="e746f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e746f-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
