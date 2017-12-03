---
title: "Configuración de los valores de tiempo de espera en un enlace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd6206d3b9445b321230bf5968891773abcac9c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-timeout-values-on-a-binding"></a><span data-ttu-id="6081b-102">Configuración de los valores de tiempo de espera en un enlace</span><span class="sxs-lookup"><span data-stu-id="6081b-102">Configuring Timeout Values on a Binding</span></span>
<span data-ttu-id="6081b-103">Hay varias configuraciones de tiempo de espera disponibles en los enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="6081b-103">There are a number of timeout settings available in WCF bindings.</span></span> <span data-ttu-id="6081b-104">Establecer estas configuraciones de tiempo de espera correctamente puede mejorar no solo el rendimiento del servicio sino también desempeñar un papel en la facilidad de uso y la seguridad del servicio.</span><span class="sxs-lookup"><span data-stu-id="6081b-104">Setting these timeout settings correctly can improve not only your service’s performance but also play a role in the usability and security of your service.</span></span> <span data-ttu-id="6081b-105">Los tiempos de espera siguientes están disponibles en los enlaces de WCF:</span><span class="sxs-lookup"><span data-stu-id="6081b-105">The following timeouts are available on WCF bindings:</span></span>  
  
1.  <span data-ttu-id="6081b-106">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="6081b-106">OpenTimeout</span></span>  
  
2.  <span data-ttu-id="6081b-107">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="6081b-107">CloseTimeout</span></span>  
  
3.  <span data-ttu-id="6081b-108">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="6081b-108">SendTimeout</span></span>  
  
4.  <span data-ttu-id="6081b-109">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="6081b-109">ReceiveTimeout</span></span>  
  
## <a name="wcf-binding-timeouts"></a><span data-ttu-id="6081b-110">Tiempos de espera de enlace de WCF</span><span class="sxs-lookup"><span data-stu-id="6081b-110">WCF Binding Timeouts</span></span>  
 <span data-ttu-id="6081b-111">Cada uno de los valores descritos en este tema se crea en el propio enlace, en código o configuración.</span><span class="sxs-lookup"><span data-stu-id="6081b-111">Each of the settings discussed in this topic are made on the binding itself, either in code or configuration.</span></span> <span data-ttu-id="6081b-112">El código siguiente muestra cómo establecer mediante programación los tiempos de espera en un enlace de WCF en el contexto de un servicio autohospedado.</span><span class="sxs-lookup"><span data-stu-id="6081b-112">The following code shows how to programmatically set timeouts on a WCF binding in the context of a self-hosted service.</span></span>  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");
    
    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));
        
        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);
        
        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();
        
        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 <span data-ttu-id="6081b-113">En el ejemplo siguiente se muestra cómo configurar tiempos de espera en un enlace en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6081b-113">The following example shows how to configure timeouts on a binding in a configuration file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00" 
                 closeTimeout="00:10:00" 
                 sendTimeout="00:10:00" 
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="6081b-114">Se puede encontrar más información sobre estos valores en la documentación de la clase <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="6081b-114">More information about these settings can be found in the documentation for the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
### <a name="client-side-timeouts"></a><span data-ttu-id="6081b-115">Tiempos de espera del lado cliente</span><span class="sxs-lookup"><span data-stu-id="6081b-115">Client-side Timeouts</span></span>  
 <span data-ttu-id="6081b-116">En el lado cliente:</span><span class="sxs-lookup"><span data-stu-id="6081b-116">On the client side:</span></span>  
  
1.  <span data-ttu-id="6081b-117">SendTimeout – se usa para inicializar OperationTimeout, que controla el proceso completo de enviar un mensaje, incluido recibir un mensaje de respuesta para una operación de servicio de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="6081b-117">SendTimeout – used to initialize the OperationTimeout, which governs the whole process of sending a message, including receiving a reply message for a request/reply service operation.</span></span> <span data-ttu-id="6081b-118">Este tiempo de espera también se aplica al enviar mensajes de respuesta de un método de contrato de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6081b-118">This timeout also applies when sending reply messages from a callback contract method.</span></span>  
  
2.  <span data-ttu-id="6081b-119">OpenTimeout – se usa al abrir canales cuando no se especifica ningún valor de tiempo de espera explícito</span><span class="sxs-lookup"><span data-stu-id="6081b-119">OpenTimeout – used when opening channels when no explicit timeout value is specified</span></span>  
  
3.  <span data-ttu-id="6081b-120">CloseTimeout – se usa al cerrar canales cuando no se especifica ningún valor de tiempo de espera explícito</span><span class="sxs-lookup"><span data-stu-id="6081b-120">CloseTimeout – used when closing channels when no explicit timeout value is specified</span></span>  
  
4.  <span data-ttu-id="6081b-121">ReceiveTimeout – no se usa</span><span class="sxs-lookup"><span data-stu-id="6081b-121">ReceiveTimeout – is not used</span></span>  
  
### <a name="service-side-timeouts"></a><span data-ttu-id="6081b-122">Tiempos de espera del servicio</span><span class="sxs-lookup"><span data-stu-id="6081b-122">Service-side Timeouts</span></span>  
 <span data-ttu-id="6081b-123">En el lado de servicio:</span><span class="sxs-lookup"><span data-stu-id="6081b-123">On the service side:</span></span>  
  
1.  <span data-ttu-id="6081b-124">SendTimeout, OpentTimeout, CloseTimeout son iguales que en el cliente</span><span class="sxs-lookup"><span data-stu-id="6081b-124">SendTimeout, OpentTimeout, CloseTimeout are the same as on the client</span></span>  
  
2.  <span data-ttu-id="6081b-125">ReceiveTimeout – lo usa el nivel de marco de trabajo de servicio para inicializar el tiempo de espera de sesión inactiva que controla cuánto tiempo puede estar inactiva una sesión antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6081b-125">ReceiveTimeout – used by the Service Framework Layer to initialize the session-idle timeout which controls how long a session can be idle before timing out.</span></span>
