---
title: Configuración de los valores de tiempo de espera en un enlace
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: 968e80bbd4b50d72d089a325f8e3fe498de2eac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185282"
---
# <a name="configuring-timeout-values-on-a-binding"></a>Configuración de los valores de tiempo de espera en un enlace
Hay varias configuraciones de tiempo de espera disponibles en los enlaces de WCF. Establecer estas configuraciones de tiempo de espera correctamente puede mejorar no solo el rendimiento del servicio sino también desempeñar un papel en la facilidad de uso y la seguridad del servicio. Los tiempos de espera siguientes están disponibles en los enlaces de WCF:  
  
1. OpenTimeout  
  
2. CloseTimeout  
  
3. SendTimeout  
  
4. ReceiveTimeout  
  
## <a name="wcf-binding-timeouts"></a>Tiempos de espera de enlace de WCF  
 Cada uno de los valores descritos en este tema se crea en el propio enlace, en código o configuración. El código siguiente muestra cómo establecer mediante programación los tiempos de espera en un enlace de WCF en el contexto de un servicio autohospedado.  
  
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
  
 En el ejemplo siguiente se muestra cómo configurar tiempos de espera en un enlace en un archivo de configuración.  
  
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
  
 Se puede encontrar más información sobre estos valores en la documentación de la clase <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="client-side-timeouts"></a>Tiempos de espera del lado cliente  
 En el lado cliente:  
  
1. SendTimeout – se usa para inicializar OperationTimeout, que controla el proceso completo de enviar un mensaje, incluido recibir un mensaje de respuesta para una operación de servicio de solicitud y respuesta. Este tiempo de espera también se aplica al enviar mensajes de respuesta de un método de contrato de devolución de llamada.  
  
2. OpenTimeout: se utiliza al abrir canales cuando no se especifica ningún valor de tiempo de espera explícito.  
  
3. CloseTimeout: se utiliza al cerrar canales cuando no se especifica ningún valor de tiempo de espera explícito.  
  
4. ReceiveTimeout : no se utiliza.  
  
### <a name="service-side-timeouts"></a>Tiempos de espera del lado del servicio  
 En el lado de servicio:  
  
1. SendTimeout, OpenTimeout, CloseTimeout son los mismos que en el cliente.  
  
2. ReceiveTimeout – lo usa el nivel de marco de trabajo de servicio para inicializar el tiempo de espera de sesión inactiva que controla cuánto tiempo puede estar inactiva una sesión antes de que se agote el tiempo de espera.
