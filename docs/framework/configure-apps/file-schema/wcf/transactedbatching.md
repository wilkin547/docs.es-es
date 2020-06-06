---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399414"
---
# \<transactedBatching>

<span data-ttu-id="4fe78-101">Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="4fe78-101">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="4fe78-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fe78-102">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fe78-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4fe78-103">Attributes and Elements</span></span>

<span data-ttu-id="4fe78-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4fe78-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fe78-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="4fe78-105">Attributes</span></span>

|<span data-ttu-id="4fe78-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="4fe78-106">Attribute</span></span>|<span data-ttu-id="4fe78-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe78-107">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="4fe78-108">Un entero que especifica el número máximo de operaciones de recepción que pueden encontrarse por lotes en una transacción.</span><span class="sxs-lookup"><span data-stu-id="4fe78-108">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="4fe78-109">El valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="4fe78-109">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4fe78-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4fe78-110">Child Elements</span></span>

<span data-ttu-id="4fe78-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4fe78-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4fe78-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4fe78-112">Parent Elements</span></span>

|<span data-ttu-id="4fe78-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe78-113">Element</span></span>|<span data-ttu-id="4fe78-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe78-114">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4fe78-115">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4fe78-115">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4fe78-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fe78-116">Remarks</span></span>

<span data-ttu-id="4fe78-117">Un transporte que se configura con procesamiento por lotes de la transacción intenta realizar varias operaciones de recepción en una transacción.</span><span class="sxs-lookup"><span data-stu-id="4fe78-117">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="4fe78-118">Haciendo esto, el costo relativamente alto de crear una transacción y confirmarla se evita en cada operación de recepción.</span><span class="sxs-lookup"><span data-stu-id="4fe78-118">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="4fe78-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fe78-119">Example</span></span>

<span data-ttu-id="4fe78-120">El ejemplo siguiente muestra cómo agregar el comportamiento por lotes llevado a cabo en un servicio en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe78-120">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4fe78-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4fe78-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
