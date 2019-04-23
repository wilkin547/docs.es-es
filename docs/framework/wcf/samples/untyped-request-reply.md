---
title: Solicitud y respuesta sin tipo
ms.date: 03/30/2017
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
ms.openlocfilehash: 6ff3a8c7f9f5c3d4731bb8946e290b265be61729
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773641"
---
# <a name="untyped-requestreply"></a>Solicitud/respuesta sin tipo
Este ejemplo muestra cómo definir contratos de operación que utilizan la clase de mensaje.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). El contrato de servicios define una operación que toma un tipo de mensaje como argumento y devuelve un mensaje. La operación recoge todos los datos necesarios para calcular la suma a partir del cuerpo del mensaje y, a continuación, la envía como cuerpo en el mensaje de retorno.  
  
```csharp
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
```  
  
 En el servicio, la operación recupera la matriz de enteros pasada en el mensaje de entrada y, a continuación, calcula la suma. Para enviar un mensaje de respuesta, el ejemplo crea un nuevo mensaje con la versión de mensaje y la acción adecuadas, y agrega la suma calculada como su cuerpo. En el siguiente ejemplo de código se muestra este caso.  
  
```csharp
public Message ComputeSum(Message request)  
{  
    //The body of the message contains a list of numbers which will be   
    //read as a int[] using GetBody<T>  
    int result = 0;  
  
    int[] inputs = request.GetBody<int[]>();  
    foreach (int i in inputs)  
    {  
        result += i;  
    }  
  
    Message response = Message.CreateMessage(request.Version,   
                                      ReplyAction, result);  
    return response;  
}  
```  
  
 El cliente utiliza código generado por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un proxy al servicio remoto. Para enviar un mensaje de solicitud, el cliente debe tener la versión del mensaje, que depende del canal subyacente. Así, crea un nuevo <xref:System.ServiceModel.OperationContextScope> en el ámbito del canal de proxy que creó, que genera un <xref:System.ServiceModel.OperationContext> con la versión de mensaje correcta en su propiedad `OutgoingMessageHeaders.MessageVersion`. El cliente pasa una matriz de entrada como el cuerpo al mensaje de solicitud y, a continuación, invoca `ComputeSum` en el proxy. El cliente recupera a continuación la suma de las entradas por las que pasó teniendo acceso al método `GetBody<T>` en el mensaje de respuesta. En el siguiente ejemplo de código se muestra este caso.  
  
```csharp
using (new OperationContextScope(client.InnerChannel))  
{  
    // Call the Sum service operation.  
    int[] values = { 1, 2, 3, 4, 5 };  
    Message request = Message.CreateMessage(  
        OperationContext.Current.OutgoingMessageHeaders.MessageVersion,   
        RequestAction, values);  
    Message reply = client.ComputeSum(request);  
    int response = reply.GetBody<int>();  
  
    Console.WriteLine("Sum of numbers passed (1,2,3,4,5) = {0}",   
                                                       response);  
}  
```  
  
 Este ejemplo es un ejemplo hospedado en web y, por tanto, solo se debe ejecutar la aplicación ejecutable del cliente. Lo siguiente es el resultado del ejemplo en el cliente.  
  
```console  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
```  
  
 Este ejemplo es un ejemplo hospedado en web. Por tanto, compruebe el vínculo proporcionado en el paso 3 para ver cómo compilar y ejecutar el ejemplo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
