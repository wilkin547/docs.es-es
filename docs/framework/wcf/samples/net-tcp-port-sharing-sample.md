---
description: 'Más información sobre: ejemplo de uso compartido de puertos net. TCP'
title: Ejemplo de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: 30b5e8896cfdd5b4174067fa37a047029bdb4502
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752163"
---
# <a name="nettcp-port-sharing-sample"></a><span data-ttu-id="1c52a-103">Ejemplo de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="1c52a-103">Net.TCP Port Sharing Sample</span></span>

<span data-ttu-id="1c52a-104">El protocolo TCP/IP utiliza un número de 16 bits, llamado "puerto", para diferenciar las conexiones en varias aplicaciones de red que se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="1c52a-104">The TCP/IP protocol uses a 16-bit number, called a port, to differentiate connections to multiple network applications running on the same machine.</span></span> <span data-ttu-id="1c52a-105">Si una aplicación está realizando escuchas en un puerto, todo el tráfico TCP para ese puerto se dirige a esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c52a-105">If an application is listening on a port, then all TCP traffic for that port goes to that application.</span></span> <span data-ttu-id="1c52a-106">Otras aplicaciones no pueden realizar escuchas en ese puerto al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="1c52a-106">Other applications cannot listen on that port at the same time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1c52a-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1c52a-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1c52a-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1c52a-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1c52a-109">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1c52a-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1c52a-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1c52a-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 <span data-ttu-id="1c52a-111">Muchos protocolos tienen un número de puerto estándar o predeterminado que utilizan.</span><span class="sxs-lookup"><span data-stu-id="1c52a-111">Many protocols have a standard or default port number that they use.</span></span> <span data-ttu-id="1c52a-112">Por ejemplo, el protocolo HTTP utiliza suele usar el puerto TCP 80.</span><span class="sxs-lookup"><span data-stu-id="1c52a-112">For example, the HTTP protocol typically uses TCP port 80.</span></span> <span data-ttu-id="1c52a-113">Internet Information Services (IIS) tiene un agente de escucha para compartir un puerto entre varias aplicaciones HTTP.</span><span class="sxs-lookup"><span data-stu-id="1c52a-113">Internet Information Services (IIS) has a listener to share a port between multiple HTTP applications.</span></span> <span data-ttu-id="1c52a-114">IIS realiza escuchas directamente en el puerto y reenvía los mensajes a la aplicación adecuada basada en la información dentro de la secuencia de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1c52a-114">IIS listens on the port directly and forwards messages to the appropriate application based on information inside the message stream.</span></span> <span data-ttu-id="1c52a-115">Esto permite a varias aplicaciones HTTP utilizar el mismo número de puerto sin tener que competir a la hora de reservar el puerto para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="1c52a-115">This allows multiple HTTP applications to use the same port number without having to compete to reserve the port for receiving messages.</span></span>  
  
 <span data-ttu-id="1c52a-116">El uso compartido de puertos de NetTcp es una característica de Windows Communication Foundation (WCF) que permite que varias aplicaciones de red compartan un único puerto.</span><span class="sxs-lookup"><span data-stu-id="1c52a-116">NetTcp Port Sharing is a Windows Communication Foundation (WCF)feature that similarly allows multiple network applications to share a single port.</span></span> <span data-ttu-id="1c52a-117">El servicio de uso compartido de puerto de NetTcp acepta las conexiones usando el protocolo de net.tcp y reenvía mensajes basados en su dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="1c52a-117">The NetTcp Port Sharing Service accepts connections using the net.tcp protocol and forwards messages based on their destination address.</span></span>  
  
 <span data-ttu-id="1c52a-118">El servicio de uso compartido de puerto de NetTcp no está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c52a-118">The NetTcp Port Sharing Service is not enabled by default.</span></span> <span data-ttu-id="1c52a-119">Antes de ejecutar este ejemplo, debe habilitar manualmente el servicio.</span><span class="sxs-lookup"><span data-stu-id="1c52a-119">Before running this sample, you must manually enable the service.</span></span> <span data-ttu-id="1c52a-120">Para obtener más información, consulte [Cómo: habilitar el servicio de uso compartido de puertos net. TCP](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="1c52a-120">For more information, see [How to: Enable the Net.TCP Port Sharing Service](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span></span> <span data-ttu-id="1c52a-121">Si el servicio está deshabilitado, se produce una excepción cuando se inicia la aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c52a-121">If the service is disabled, an exception is thrown when the server application is started.</span></span>  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 <span data-ttu-id="1c52a-122">El uso compartido del puerto se habilita en el servidor estableciendo la propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> del enlace <xref:System.ServiceModel.NetTcpBinding> o el elemento de enlace <xref:System.ServiceModel.Channels.TcpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="1c52a-122">Port sharing is enabled on the server by setting the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property of the <xref:System.ServiceModel.NetTcpBinding> binding or the <xref:System.ServiceModel.Channels.TcpTransportBindingElement> binding element.</span></span> <span data-ttu-id="1c52a-123">El cliente no tiene que saber cómo se ha configurado el uso compartido de puerto para usarlo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1c52a-123">The client does not have to know how port sharing has been configured to use it on the server.</span></span>  
  
## <a name="enabling-port-sharing"></a><span data-ttu-id="1c52a-124">Cómo habilitar el uso compartido del puerto</span><span class="sxs-lookup"><span data-stu-id="1c52a-124">Enabling Port Sharing</span></span>  

 <span data-ttu-id="1c52a-125">El código siguiente muestra cómo habilitar el uso compartido del puerto en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1c52a-125">The following code demonstrates enabling port sharing on the server.</span></span> <span data-ttu-id="1c52a-126">Inicia una instancia del servicio `ICalculator` en un puerto fijo con una ruta de acceso del URI aleatoria.</span><span class="sxs-lookup"><span data-stu-id="1c52a-126">It starts an instance of the `ICalculator` service on a fixed port with a random URI path.</span></span> <span data-ttu-id="1c52a-127">Aunque dos servicios pueden compartir el mismo puerto, sus direcciones de punto de conexión totales deben seguir siendo únicas de manera que el servicio de uso compartido de puertos de NetTcp puede enrutar los mensajes a la aplicación correcta.</span><span class="sxs-lookup"><span data-stu-id="1c52a-127">Even though two services can share the same port, their overall endpoint addresses still must be unique so that the NetTcp Port Sharing Service can route messages to the correct application.</span></span>  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address = $"net.tcp://localhost:9000/calculator/{salt}";
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 <span data-ttu-id="1c52a-128">Con el uso compartido del puerto habilitado, puede ejecutar el servicio varias veces sin tener un conflicto sobre el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="1c52a-128">With port sharing enabled, you can run the service multiple times without having a conflict over the port number.</span></span> <span data-ttu-id="1c52a-129">Si cambia el código para deshabilitar el uso compartido del puerto, iniciar hasta un máximo de dos copias del servicio da como resultado que la segunda fracase con un <xref:System.ServiceModel.AddressAlreadyInUseException>.</span><span class="sxs-lookup"><span data-stu-id="1c52a-129">If you change the code to disable port sharing, starting up two copies of the service results in the second failing with an <xref:System.ServiceModel.AddressAlreadyInUseException>.</span></span>  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="1c52a-130">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c52a-130">Running the Sample</span></span>  

 <span data-ttu-id="1c52a-131">Puede utilizar el cliente de pruebas para comprobar que los mensajes se enrutan correctamente a los servicios que comparten el puerto.</span><span class="sxs-lookup"><span data-stu-id="1c52a-131">You can use the test client to check that messages are correctly routed to services sharing the port.</span></span>  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = $"net.tcp://localhost:9000/calculator/{salt}";
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 <span data-ttu-id="1c52a-132">Cada instancia del servicio imprime su número y dirección únicos.</span><span class="sxs-lookup"><span data-stu-id="1c52a-132">Each instance of the service prints out its unique number and address.</span></span> <span data-ttu-id="1c52a-133">Por ejemplo, puede ver el texto siguiente al ejecutar service.exe.</span><span class="sxs-lookup"><span data-stu-id="1c52a-133">For instance, you may see the following text when you run service.exe.</span></span>  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="1c52a-134">Introduzca el número del servicio que ve aquí cuando ejecute client.exe.</span><span class="sxs-lookup"><span data-stu-id="1c52a-134">Enter the service number you see here when you run client.exe.</span></span>  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="1c52a-135">Este ejemplo se puede ejecutar en una configuración de equipos cruzada cambiando la dirección generada que utiliza el cliente.</span><span class="sxs-lookup"><span data-stu-id="1c52a-135">This sample can be run in a cross-machine configuration by changing the generated address that the client uses.</span></span> <span data-ttu-id="1c52a-136">En el archivo Client.cs, cambie la cadena de formato de dirección de punto de conexión para que coincida con la nueva dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="1c52a-136">In the Client.cs, change the endpoint address format string to match the new address of your service.</span></span> <span data-ttu-id="1c52a-137">Reemplace cualquier referencia al "host local" con la dirección IP del equipo del servidor.</span><span class="sxs-lookup"><span data-stu-id="1c52a-137">Replace any references to "localhost" with the IP address of the server machine.</span></span> <span data-ttu-id="1c52a-138">Debe recompilar el ejemplo después de realizar esta modificación.</span><span class="sxs-lookup"><span data-stu-id="1c52a-138">You must recompile the sample after making this change.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1c52a-139">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c52a-139">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1c52a-140">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="1c52a-140">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="1c52a-141">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c52a-141">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="1c52a-142">Habilite el servicio de uso compartido del puerto de NetTcp tal y como se ha descrito previamente en la sección de introducción.</span><span class="sxs-lookup"><span data-stu-id="1c52a-142">Enable the NetTcp Port Sharing Service as previously described in the introduction section.</span></span>  
  
4. <span data-ttu-id="1c52a-143">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c52a-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="1c52a-144">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1c52a-144">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="1c52a-145">Los detalles concretos para ejecutar este ejemplo se han incluido previamente en la sección Ejecución del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1c52a-145">Specific details for running this sample are included previously in the Running the Sample section.</span></span>  
