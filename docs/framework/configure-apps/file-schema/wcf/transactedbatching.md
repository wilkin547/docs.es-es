---
description: 'Más información acerca de: <transactedBatching>'
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 9a57226c3a2f2b026c69324e37b00e87fd3dd693
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773698"
---
# \<transactedBatching>

<span data-ttu-id="ea787-102">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="ea787-102">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="ea787-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea787-103">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea787-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea787-104">Attributes and Elements</span></span>

<span data-ttu-id="ea787-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea787-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea787-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea787-106">Attributes</span></span>

|<span data-ttu-id="ea787-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ea787-107">Attribute</span></span>|<span data-ttu-id="ea787-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea787-108">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="ea787-109">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="ea787-109">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="ea787-110">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="ea787-110">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ea787-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea787-111">Child Elements</span></span>

<span data-ttu-id="ea787-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea787-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ea787-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea787-113">Parent Elements</span></span>

|<span data-ttu-id="ea787-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea787-114">Element</span></span>|<span data-ttu-id="ea787-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea787-115">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ea787-116">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ea787-116">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ea787-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ea787-117">Remarks</span></span>

<span data-ttu-id="ea787-118">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="ea787-118">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="ea787-119">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="ea787-119">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="ea787-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea787-120">Example</span></span>

<span data-ttu-id="ea787-121">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ea787-121">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ea787-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea787-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
