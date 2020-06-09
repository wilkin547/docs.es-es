---
title: Ejemplo de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: 6c196380951d0da912cd937e3ebc38a03f80489c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584317"
---
# <a name="nettcp-port-sharing-sample"></a>Ejemplo de uso compartido de puertos Net.TCP
El protocolo TCP/IP utiliza un número de 16 bits, llamado "puerto", para diferenciar las conexiones en varias aplicaciones de red que se ejecutan en el mismo equipo. Si una aplicación está realizando escuchas en un puerto, todo el tráfico TCP para ese puerto se dirige a esa aplicación. Otras aplicaciones no pueden realizar escuchas en ese puerto al mismo tiempo.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 Muchos protocolos tienen un número de puerto estándar o predeterminado que utilizan. Por ejemplo, el protocolo HTTP utiliza suele usar el puerto TCP 80. Internet Information Services (IIS) tiene un agente de escucha para compartir un puerto entre varias aplicaciones HTTP. IIS realiza escuchas directamente en el puerto y reenvía los mensajes a la aplicación adecuada basada en la información dentro de la secuencia de mensajes. Esto permite a varias aplicaciones HTTP utilizar el mismo número de puerto sin tener que competir a la hora de reservar el puerto para recibir mensajes.  
  
 El uso compartido de puertos de NetTcp es una característica de Windows Communication Foundation (WCF) que permite que varias aplicaciones de red compartan un único puerto. El servicio de uso compartido de puerto de NetTcp acepta las conexiones usando el protocolo de net.tcp y reenvía mensajes basados en su dirección de destino.  
  
 El servicio de uso compartido de puerto de NetTcp no está habilitado de forma predeterminada. Antes de ejecutar este ejemplo, debe habilitar manualmente el servicio. Para obtener más información, consulte [Cómo: habilitar el servicio de uso compartido de puertos net. TCP](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md). Si el servicio está deshabilitado, se produce una excepción cuando se inicia la aplicación de servidor.  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 El uso compartido del puerto se habilita en el servidor estableciendo la propiedad <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> del enlace <xref:System.ServiceModel.NetTcpBinding> o el elemento de enlace <xref:System.ServiceModel.Channels.TcpTransportBindingElement>. El cliente no tiene que saber cómo se ha configurado el uso compartido de puerto para usarlo en el servidor.  
  
## <a name="enabling-port-sharing"></a>Cómo habilitar el uso compartido del puerto  
 El código siguiente muestra cómo habilitar el uso compartido del puerto en el servidor. Inicia una instancia del servicio `ICalculator` en un puerto fijo con una ruta de acceso del URI aleatoria. Aunque dos servicios pueden compartir el mismo puerto, sus direcciones de punto de conexión totales deben seguir siendo únicas de manera que el servicio de uso compartido de puertos de NetTcp puede enrutar los mensajes a la aplicación correcta.  

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

 Con el uso compartido del puerto habilitado, puede ejecutar el servicio varias veces sin tener un conflicto sobre el número de puerto. Si cambia el código para deshabilitar el uso compartido del puerto, iniciar hasta un máximo de dos copias del servicio da como resultado que la segunda fracase con un <xref:System.ServiceModel.AddressAlreadyInUseException>.  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Puede utilizar el cliente de pruebas para comprobar que los mensajes se enrutan correctamente a los servicios que comparten el puerto.  

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

 Cada instancia del servicio imprime su número y dirección únicos. Por ejemplo, puede ver el texto siguiente al ejecutar service.exe.  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 Introduzca el número del servicio que ve aquí cuando ejecute client.exe.  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Este ejemplo se puede ejecutar en una configuración de equipos cruzada cambiando la dirección generada que utiliza el cliente. En el archivo Client.cs, cambie la cadena de formato de dirección de punto de conexión para que coincida con la nueva dirección del servicio. Reemplace cualquier referencia al "host local" con la dirección IP del equipo del servidor. Debe recompilar el ejemplo después de realizar esta modificación.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Instale ASP.NET 4,0 con el siguiente comando.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Habilite el servicio de uso compartido del puerto de NetTcp tal y como se ha descrito previamente en la sección de introducción.  
  
4. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
5. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md). Los detalles concretos para ejecutar este ejemplo se han incluido previamente en la sección Ejecución del ejemplo.  
