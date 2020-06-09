---
title: Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 0775de90903aed27a8d0006614a4b6f2d857eee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597103"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="34e55-102">Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server</span><span class="sxs-lookup"><span data-stu-id="34e55-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="34e55-103">Puede integrar aplicaciones de Message Queuing (MSMQ) existentes con aplicaciones Windows Communication Foundation (WCF) mediante el enlace de integración de MSMQ para convertir mensajes de MSMQ a y desde mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="34e55-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="34e55-104">Esto le permite llamar a aplicaciones de receptor de MSMQ desde clientes de WCF, así como llamar a servicios WCF desde aplicaciones de remitente MSMQ.</span><span class="sxs-lookup"><span data-stu-id="34e55-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="34e55-105">En esta sección, se explica cómo usar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un cliente WCF y un servicio de aplicación MSMQ escrito con System. Messaging y (2) un cliente de aplicación MSMQ y un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="34e55-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="34e55-106">Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de receptor de MSMQ desde un cliente de WCF, vea el ejemplo de [Windows Communication Foundation a Message Queue Server](../samples/wcf-to-message-queuing.md) .</span><span class="sxs-lookup"><span data-stu-id="34e55-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="34e55-107">Para obtener un ejemplo completo que muestra cómo llamar a un servicio WCF desde un cliente MSMQ, vea el ejemplo de [Message Queue Server para Windows Communication Foundation](../samples/message-queuing-to-wcf.md) .</span><span class="sxs-lookup"><span data-stu-id="34e55-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="34e55-108">Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ</span><span class="sxs-lookup"><span data-stu-id="34e55-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1. <span data-ttu-id="34e55-109">Defina una interfaz que defina el contrato de servicio para el servicio WCF que recibe los mensajes en cola de una aplicación de remitente MSMQ, tal como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="34e55-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. <span data-ttu-id="34e55-110">Implemente la interfaz y aplique el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="34e55-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. <span data-ttu-id="34e55-111">Cree un archivo de configuración que especifique <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="34e55-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4. <span data-ttu-id="34e55-112">Cree una instancia de un objeto <xref:System.ServiceModel.ServiceHost> que utilice el enlace configurado.</span><span class="sxs-lookup"><span data-stu-id="34e55-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="34e55-113">Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ</span><span class="sxs-lookup"><span data-stu-id="34e55-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1. <span data-ttu-id="34e55-114">Defina una interfaz que defina el contrato de servicio para el cliente de WCF que envía los mensajes en cola al receptor de MSMQ, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="34e55-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. <span data-ttu-id="34e55-115">Defina una clase de cliente que el cliente de WCF use para llamar al receptor de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="34e55-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. <span data-ttu-id="34e55-116">Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="34e55-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. <span data-ttu-id="34e55-117">Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="34e55-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="34e55-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e55-118">See also</span></span>

- [<span data-ttu-id="34e55-119">Información general de colas</span><span class="sxs-lookup"><span data-stu-id="34e55-119">Queues Overview</span></span>](queues-overview.md)
- [<span data-ttu-id="34e55-120">Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF</span><span class="sxs-lookup"><span data-stu-id="34e55-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="34e55-121">Windows Communication Foundation a Message Queuing</span><span class="sxs-lookup"><span data-stu-id="34e55-121">Windows Communication Foundation to Message Queuing</span></span>](../samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="34e55-122">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="34e55-122">Installing Message Queuing (MSMQ)</span></span>](../samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="34e55-123">Message Queuing a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="34e55-123">Message Queuing to Windows Communication Foundation</span></span>](../samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="34e55-124">Seguridad de mensajes mediante Message Queuing</span><span class="sxs-lookup"><span data-stu-id="34e55-124">Message Security over Message Queuing</span></span>](../samples/message-security-over-message-queuing.md)
