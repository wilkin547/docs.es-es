---
description: Más información acerca de cómo crear aplicaciones de multidifusión mediante el transporte UDP
title: Crear aplicaciones de multidifusión mediante el transporte UDP
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: cea76bc1256d52dabebe525b0fdd8b64c08f9e7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705166"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="474cc-103">Crear aplicaciones de multidifusión mediante el transporte UDP</span><span class="sxs-lookup"><span data-stu-id="474cc-103">Creating Multicasting Applications using the UDP Transport</span></span>

<span data-ttu-id="474cc-104">Las aplicaciones de multidifusión envían pequeños mensajes a un gran número de destinatarios al mismo tiempo sin necesidad de establecer conexiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="474cc-104">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="474cc-105">El énfasis de esas aplicaciones es la velocidad sobre la conconfiabilidad.</span><span class="sxs-lookup"><span data-stu-id="474cc-105">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="474cc-106">Es decir es más importante enviar datos puntualmente que asegurarse de que cualquier mensaje concreto se reciba realmente.</span><span class="sxs-lookup"><span data-stu-id="474cc-106">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="474cc-107">WCF admite ahora la escritura de aplicaciones de multidifusión mediante <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="474cc-107">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="474cc-108">Este transporte es útil en escenarios donde un servicio necesita enviar pequeños mensajes a varios clientes simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="474cc-108">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="474cc-109">Una aplicación de cotización bursátil es un ejemplo de este tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="474cc-109">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="474cc-110">Implementar una aplicación de multidifusión</span><span class="sxs-lookup"><span data-stu-id="474cc-110">Implementing a Multicast Application</span></span>  

 <span data-ttu-id="474cc-111">Para implementar una aplicación de multidifusión, defina un contrato de servicio y para cada componente de software que necesite responder a los mensajes de multidifusión, implemente el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="474cc-111">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="474cc-112">Por ejemplo, una aplicación de cotización bursátil podría definir un contrato de servicio:</span><span class="sxs-lookup"><span data-stu-id="474cc-112">For example, a stock ticker application might define a service contract:</span></span>  
  
```csharp
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 <span data-ttu-id="474cc-113">Cada aplicación que desea recibir mensajes de multidifusión debe hospedar un servicio que expone esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="474cc-113">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="474cc-114">Por ejemplo, aquí tiene un ejemplo de código que muestra cómo recibir mensajes de multidifusión:</span><span class="sxs-lookup"><span data-stu-id="474cc-114">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
```csharp
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 <span data-ttu-id="474cc-115">La aplicación especifica la dirección UDP en la que todos los servicios escucharán.</span><span class="sxs-lookup"><span data-stu-id="474cc-115">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="474cc-116">Se crea un nuevo <xref:System.ServiceModel.ServiceHost> y un punto de conexión de servicio se expone mediante <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="474cc-116">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="474cc-117"><xref:System.ServiceModel.ServiceHost> se abre y empezará a escuchar mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="474cc-117">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="474cc-118">En este tipo de escenario es el cliente quien envía realmente mensajes de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="474cc-118">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="474cc-119">Cada servicio que está escuchando en la dirección UDP correcta recibirá los mensajes de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="474cc-119">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="474cc-120">A continuación se muestra un ejemplo de un cliente que envía mensajes de multidifusión:</span><span class="sxs-lookup"><span data-stu-id="474cc-120">Here is an example of a client that sends out multicast messages:</span></span>  
  
```csharp
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine($"sent stock info at {DateTime.Now}");
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 <span data-ttu-id="474cc-121">Este código genera información bursátil y usa el contrato de servicio IStockTicker para enviar mensajes de multidifusión para llamar a servicios que escuchan en la dirección UDP correcta.</span><span class="sxs-lookup"><span data-stu-id="474cc-121">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="474cc-122">Mensajería UDP y de confianza</span><span class="sxs-lookup"><span data-stu-id="474cc-122">UDP and Reliable Messaging</span></span>  

  <span data-ttu-id="474cc-123">El enlace UDP no admite mensajería de confianza debido a la naturaleza ligera del protocolo UDP.</span><span class="sxs-lookup"><span data-stu-id="474cc-123">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="474cc-124">Si necesita confirmar que los mensajes son recibidos por un punto de conexión remoto, use un transporte que admita mensajería de confianza como HTTP o TCP.</span><span class="sxs-lookup"><span data-stu-id="474cc-124">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="474cc-125">Para obtener más información acerca de la mensajería de confianza, vea <https://go.microsoft.com/fwlink/?LinkId=231830> .</span><span class="sxs-lookup"><span data-stu-id="474cc-125">For more information about reliable messaging, see <https://go.microsoft.com/fwlink/?LinkId=231830>.</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="474cc-126">Mensajería bidireccional de multidifusión</span><span class="sxs-lookup"><span data-stu-id="474cc-126">Two-way Multicast Messaging</span></span>  

 <span data-ttu-id="474cc-127">Mientras que los mensajes de multidifusión suelen ser unidireccionales, el UdpBinding admite intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="474cc-127">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="474cc-128">Los mensajes enviados mediante el transporte UDP contienen direcciones From y To.</span><span class="sxs-lookup"><span data-stu-id="474cc-128">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="474cc-129">Se ha de tener cuidado al usar la dirección From porque podría cambiarse malintencionadamente en la ruta.</span><span class="sxs-lookup"><span data-stu-id="474cc-129">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="474cc-130">La dirección se puede comprobar mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="474cc-130">The address can be checked using the following code:</span></span>  
  
```csharp
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 <span data-ttu-id="474cc-131">Este código comprueba el primer byte de la dirección From para ver si contiene 0xE0, lo que significa que la dirección es una dirección de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="474cc-131">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="474cc-132">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="474cc-132">Security Considerations</span></span>  

 <span data-ttu-id="474cc-133">Al escuchar mensajes de multidifusión se envía un paquete ICMP al enrutador para notificarle que está escuchando en la dirección de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="474cc-133">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="474cc-134">Cualquier usuario de la subred local que tenga permisos podría escuchar estos tipos de paquetes y determinar en qué dirección de multidifusión y puerto se está escuchando.</span><span class="sxs-lookup"><span data-stu-id="474cc-134">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="474cc-135">No use la dirección IP del remitente para ningún propósito de seguridad.</span><span class="sxs-lookup"><span data-stu-id="474cc-135">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="474cc-136">Esta información se puede suplantar y puede hacer que una aplicación envíe respuestas al equipo incorrecto.</span><span class="sxs-lookup"><span data-stu-id="474cc-136">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="474cc-137">Una manera de resolver esta amenaza es habilitar la seguridad de nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="474cc-137">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="474cc-138">En el nivel de red también se puede usar IPsec (protocolo de seguridad de Internet) o NAP (Protección de acceso a redes).</span><span class="sxs-lookup"><span data-stu-id="474cc-138">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
