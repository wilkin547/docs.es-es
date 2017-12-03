---
title: "Cómo: Intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queuing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b18dab37a18723671cebf51c3cc943b907b38a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="ef3f4-102">Cómo: Intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queuing</span><span class="sxs-lookup"><span data-stu-id="ef3f4-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="ef3f4-103">Puede integrar aplicaciones Message Queuing existentes (MSMQ) con aplicaciones de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizando el enlace de integración de MSMQ para convertir los mensajes de MSMQ a y desde mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef3f4-103">You can integrate existing Message Queuing (MSMQ) applications with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications by using the MSMQ integration binding to convert MSMQ messages to and from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messages.</span></span> <span data-ttu-id="ef3f4-104">Esto le permite llamar a aplicaciones de receptor de MSMQ desde clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], así como llamar a servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] desde aplicaciones de remitente de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-104">This allows you to call into MSMQ receiver applications from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients as well as call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="ef3f4-105">En esta sección, explicamos cómo utilizar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un servicio de aplicación de MSMQ escrito al usar System.Messaging y (2) un cliente de aplicación de MSMQ y un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef3f4-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="ef3f4-106">Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de receptor MSMQ desde una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente, consulte la [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="ef3f4-107">Para obtener un ejemplo completo que muestra cómo llamar a un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio desde un cliente MSMQ, vea el [Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-107">For a complete sample that demonstrates how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="ef3f4-108">Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ</span><span class="sxs-lookup"><span data-stu-id="ef3f4-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="ef3f4-109">Defina una interfaz que defina el contrato de servicio para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que recibe los mensajes en cola desde una aplicación remitente de MSMQ, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-109">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="ef3f4-110">Implemente la interfaz y aplique el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="ef3f4-111">Cree un archivo de configuración que especifique <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="ef3f4-112">Cree una instancia de un objeto <xref:System.ServiceModel.ServiceHost> que utilice el enlace configurado.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="ef3f4-113">Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ</span><span class="sxs-lookup"><span data-stu-id="ef3f4-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="ef3f4-114">Defina una interfaz que defina el contrato de servicio para el cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que envía mensajes en cola al receptor de MSMQ, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-114">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="ef3f4-115">Defina una clase de cliente que el cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usará para llamar al receptor de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-115">Define a client class that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="ef3f4-116">Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="ef3f4-117">Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ef3f4-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ef3f4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef3f4-118">See Also</span></span>  
 [<span data-ttu-id="ef3f4-119">Información general de colas</span><span class="sxs-lookup"><span data-stu-id="ef3f4-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="ef3f4-120">Cómo: intercambiar mensajes con extremos de WCF en cola</span><span class="sxs-lookup"><span data-stu-id="ef3f4-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="ef3f4-121">Windows Communication Foundation a Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="ef3f4-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="ef3f4-122">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="ef3f4-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="ef3f4-123">Message Queue Server de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ef3f4-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="ef3f4-124">Seguridad de mensajes mediante Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="ef3f4-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
