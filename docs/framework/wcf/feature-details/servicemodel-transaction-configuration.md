---
description: 'Más información acerca de: configuración de transacciones de ServiceModel'
title: Configuración de la transacción ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 260e3cbe94ce0d22887554705134eef72a031981
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793472"
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="e25ff-103">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e25ff-103">ServiceModel Transaction Configuration</span></span>

<span data-ttu-id="e25ff-104">Windows Communication Foundation (WCF) proporciona tres atributos para configurar transacciones para un servicio: `transactionFlow` , `transactionProtocol` y `transactionTimeout` .</span><span class="sxs-lookup"><span data-stu-id="e25ff-104">Windows Communication Foundation (WCF) provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="e25ff-105">Configuración de transactionFlow</span><span class="sxs-lookup"><span data-stu-id="e25ff-105">Configuring transactionFlow</span></span>  

 <span data-ttu-id="e25ff-106">La mayoría de los enlaces predefinidos que WCF proporciona contienen los `transactionFlow` `transactionProtocol` atributos y, de modo que se puede configurar el enlace para aceptar las transacciones entrantes de un punto de conexión concreto mediante un protocolo de flujo de transacciones específico.</span><span class="sxs-lookup"><span data-stu-id="e25ff-106">Most of the predefined bindings WCF provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="e25ff-107">Además, puede usar el elemento `transactionFlow` y su atributo `transactionProtocol` para compilar su propio enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e25ff-107">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> <span data-ttu-id="e25ff-108">Para obtener más información acerca de cómo establecer los elementos de configuración, vea [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) y el [esquema de configuración de WCF](../../configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="e25ff-108">For more information about setting the configuration elements, see [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) and [WCF Configuration Schema](../../configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="e25ff-109">El atributo `transactionFlow` especifica si el flujo de transacciones está habilitado para los extremos de servicio que utilizan el enlace.</span><span class="sxs-lookup"><span data-stu-id="e25ff-109">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="e25ff-110">Configuración de transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="e25ff-110">Configuring transactionProtocol</span></span>  

 <span data-ttu-id="e25ff-111">El atributo `transactionProtocol` especifica el protocolo de transacción a utilizar con extremos de servicio que utilizan el enlace.</span><span class="sxs-lookup"><span data-stu-id="e25ff-111">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="e25ff-112">El siguiente es un ejemplo de una sección de configuración que configura el enlace especificado para que admita el flujo de transacciones, así como un uso del protocolo WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="e25ff-112">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="e25ff-113">Configuración de transactionTimeout</span><span class="sxs-lookup"><span data-stu-id="e25ff-113">Configuring transactionTimeout</span></span>  

 <span data-ttu-id="e25ff-114">Puede configurar el `transactionTimeout` atributo para el servicio WCF en el `behavior` elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e25ff-114">You can configure the `transactionTimeout` attribute for your WCF service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="e25ff-115">El siguiente código muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="e25ff-115">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="e25ff-116">El atributo `transactionTimeout` especifica el período dentro del que una nueva transacción creada en el servicio debe completarse.</span><span class="sxs-lookup"><span data-stu-id="e25ff-116">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="e25ff-117">Se utiliza como tiempo de espera <xref:System.Transactions.TransactionScope> para cualquier operación que establezca una nueva transacción y si se aplica <xref:System.ServiceModel.OperationBehaviorAttribute>, la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="e25ff-117">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="e25ff-118">El tiempo de espera especifica la duración desde la creación de la transacción hasta la finalización de la fase 1 en el protocolo de confirmación de dos fases.</span><span class="sxs-lookup"><span data-stu-id="e25ff-118">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="e25ff-119">Si este atributo se establece dentro de una sección de configuración de `service`, debería aplicar al menos un método del servicio correspondiente con <xref:System.ServiceModel.OperationBehaviorAttribute>, en el que la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="e25ff-119">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="e25ff-120">Tenga en cuenta que el valor de tiempo de espera usado es el valor más pequeño entre este ajuste de configuración de `transactionTimeout` y cualquier propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="e25ff-120">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25ff-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e25ff-121">See also</span></span>

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="e25ff-122">Esquema de configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="e25ff-122">WCF Configuration Schema</span></span>](../../configure-apps/file-schema/wcf/index.md)
