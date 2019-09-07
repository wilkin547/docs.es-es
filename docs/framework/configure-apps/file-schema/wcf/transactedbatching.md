---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399414"
---
# <a name="transactedbatching"></a><span data-ttu-id="d2370-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="d2370-101">\<transactedBatching></span></span>

<span data-ttu-id="d2370-102">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="d2370-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="d2370-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2370-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2370-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2370-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d2370-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2370-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d2370-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2370-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d2370-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2370-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d2370-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transactedBatching**</span><span class="sxs-lookup"><span data-stu-id="d2370-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d2370-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2370-109">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2370-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2370-110">Attributes and Elements</span></span>

<span data-ttu-id="d2370-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d2370-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d2370-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2370-112">Attributes</span></span>

|<span data-ttu-id="d2370-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d2370-113">Attribute</span></span>|<span data-ttu-id="d2370-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d2370-114">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="d2370-115">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="d2370-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="d2370-116">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="d2370-116">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d2370-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2370-117">Child Elements</span></span>

<span data-ttu-id="d2370-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2370-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2370-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2370-119">Parent Elements</span></span>

|<span data-ttu-id="d2370-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2370-120">Element</span></span>|<span data-ttu-id="d2370-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d2370-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2370-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d2370-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d2370-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d2370-123">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d2370-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2370-124">Remarks</span></span>

<span data-ttu-id="d2370-125">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="d2370-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="d2370-126">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="d2370-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="d2370-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2370-127">Example</span></span>

<span data-ttu-id="d2370-128">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d2370-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d2370-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2370-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
