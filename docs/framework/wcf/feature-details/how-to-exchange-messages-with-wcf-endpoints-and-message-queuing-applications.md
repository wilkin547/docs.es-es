---
title: 'Cómo: Intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queuing'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 807a34ac50ea317ace42ec12eddcd9ec7cf3736b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491084"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="365e0-102">Cómo: Intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queuing</span><span class="sxs-lookup"><span data-stu-id="365e0-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="365e0-103">Puede integrar las aplicaciones existentes de Message Queuing (MSMQ) con aplicaciones de Windows Communication Foundation (WCF) mediante el enlace de integración de MSMQ para convertir los mensajes MSMQ a y desde los mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="365e0-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="365e0-104">Esto permite llamar a las aplicaciones de receptor MSMQ desde clientes de WCF, así como llamar a servicios WCF desde aplicaciones de remitente MSMQ.</span><span class="sxs-lookup"><span data-stu-id="365e0-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="365e0-105">En esta sección se explica cómo usar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para la comunicación en cola entre (1) un cliente WCF y un servicio de aplicación de MSMQ escrito mediante System.Messaging y (2) un cliente de aplicación de MSMQ y un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="365e0-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="365e0-106">Para obtener un ejemplo completo que muestra cómo llamar a una aplicación de receptor MSMQ desde un cliente de WCF, consulte el [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="365e0-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="365e0-107">Para obtener un ejemplo completo que muestra cómo llamar a un servicio WCF desde un cliente MSMQ, consulte la [Message Queue Server de Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="365e0-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="365e0-108">Para crear un servicio WCF que reciba mensajes desde un cliente de MSMQ</span><span class="sxs-lookup"><span data-stu-id="365e0-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="365e0-109">Defina una interfaz que define el contrato de servicio para el servicio WCF que recibe mensajes en cola desde una aplicación de remitente MSMQ, tal como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="365e0-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="365e0-110">Implemente la interfaz y aplique el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> a la clase, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="365e0-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="365e0-111">Cree un archivo de configuración que especifique <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="365e0-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="365e0-112">Cree una instancia de un objeto <xref:System.ServiceModel.ServiceHost> que utilice el enlace configurado.</span><span class="sxs-lookup"><span data-stu-id="365e0-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="365e0-113">Para crear un cliente de WCF que envíe mensajes a una aplicación de receptor de MSMQ</span><span class="sxs-lookup"><span data-stu-id="365e0-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="365e0-114">Defina una interfaz que define el contrato de servicio para el cliente WCF que envía los mensajes en cola al receptor de MSMQ, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="365e0-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="365e0-115">Defina una clase de cliente que utiliza el cliente WCF para llamar al receptor de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="365e0-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="365e0-116">Cree una configuración que especifique el uso del enlace MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="365e0-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="365e0-117">Cree una instancia de la clase de cliente y llame al método definido por el servicio de recepción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="365e0-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="365e0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="365e0-118">See Also</span></span>  
 [<span data-ttu-id="365e0-119">Información general de colas</span><span class="sxs-lookup"><span data-stu-id="365e0-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="365e0-120">Intercambio de mensajes en cola con puntos de conexión de WCF</span><span class="sxs-lookup"><span data-stu-id="365e0-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="365e0-121">Windows Communication Foundation a Message Queuing</span><span class="sxs-lookup"><span data-stu-id="365e0-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="365e0-122">Instalación de Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="365e0-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="365e0-123">Message Queuing a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="365e0-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="365e0-124">Seguridad de mensajes mediante Message Queuing</span><span class="sxs-lookup"><span data-stu-id="365e0-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
