---
description: 'Más información sobre: transporte y codificación de enlace personalizado'
title: Transporte y codificación de enlace personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: d579414d77836abecc685b758e81d0775c3ca142
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732688"
---
# <a name="custom-binding-transport-and-encoding"></a>Transporte y codificación de enlace personalizado

Un enlace personalizado se define mediante una lista ordenada de elementos de enlace discretos. Este ejemplo muestra cómo configurar un enlace personalizado con varios elementos de codificación de mensajes y transporte.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo se basa en el [propio host](self-host.md)y se ha modificado para configurar tres puntos de conexión para que admitan transportes http, TCP y NamedPipe con enlaces personalizados. La configuración del cliente se modificó de igual forma y el código de cliente cambió para comunicarse con cada uno de los tres puntos de conexión.  
  
 El ejemplo muestra cómo configurar un enlace personalizado que admite un transporte determinado y la codificación de mensajes. Esto se logra configurando un transporte y una codificación de mensajes para el elemento `binding`. El orden de los elementos de enlace es importante en la definición de un enlace personalizado, ya que cada uno representa una capa en la pila del canal (vea [enlaces personalizados](../extending/custom-bindings.md)). Este ejemplo configura tres enlaces personalizados: un transporte HTTP con codificación de texto, un transporte TCP con codificación de texto y un transporte NamedPipe con una codificación binaria.  
  
 La configuración de servicio define los enlaces personalizados de la siguiente forma:  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 Al ejecutar el ejemplo, las solicitudes de operación y las respuestas se muestran en la ventana de la consola del cliente y del servicio. El cliente se comunica con cada uno de los tres puntos de conexión, teniendo acceso primero a HTTP, después a TCP y finalmente a NamedPipe. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
 El enlace `namedPipeTransport` no admite las operaciones de equipo a equipo. Sólo se utiliza para la comunicación en el mismo equipo. Por consiguiente, al ejecutar el ejemplo en un escenario con varios equipos, marque como comentarios las líneas siguientes en el archivo de código de cliente:  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la edición de C#, C++ o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
