---
title: Contrato de mensaje predeterminado
ms.date: 03/30/2017
helpviewer_keywords:
- Message Contract
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
ms.openlocfilehash: 404fd9ddc911327bbc09c65d74da22bd88d08e2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602575"
---
# <a name="default-message-contract"></a>Contrato de mensaje predeterminado
El ejemplo de contrato de mensaje predeterminado muestra un servicio donde un mensaje personalizado definido por el usuario se pasa a las operaciones de servicio y desde ellas. Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa una interfaz de calculadora como un servicio con tipo. En lugar de las operaciones de servicio individuales para la suma, resta, multiplicación y división utilizadas en el [Introducción](getting-started-sample.md), este ejemplo pasa un mensaje personalizado que contiene los operandos y el operador, y devuelve el resultado del cálculo aritmético.  
  
 El cliente es un programa de la consola (.exe) e Internet Information Services (IIS) hospeda la biblioteca de servicio. La actividad del cliente es visible en la ventana de la consola.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En el servicio, se define una única operación de servicio que acepta y devuelve mensajes personalizados de tipo `MyMessage`. Aunque en este ejemplo los mensajes de solicitud y respuesta son del mismo tipo, podrían ser desde luego contratos de mensaje diferentes si fuera necesario.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
```  
  
 Se define el mensaje personalizado `MyMessage` en una clase anotada con los atributos <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>. Sólo se usa el tercer constructor en este ejemplo. Utilizar los contratos de mensaje le permite ejercer control completo sobre el mensaje SOAP. En este ejemplo, el atributo <xref:System.ServiceModel.MessageHeaderAttribute> se utiliza para colocar `Operation` en un encabezado SOAP. Los operandos `N1`, `N2` y `Result` aparecen dentro del cuerpo de SOAP porque tienen el atributo <xref:System.ServiceModel.MessageBodyMemberAttribute> aplicado.  
  
```csharp
[MessageContract]  
public class MyMessage  
{  
    private string operation;  
    private double n1;  
    private double n2;  
    private double result;  
  
    //Constructor - create an empty message.  
  
    public MyMessage() {}  
  
    //Constructor - create a message and populate its members.  
  
    public MyMessage(double n1, double n2, string operation,
                     double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    //Constructor - create a message from another message.  
  
    public MyMessage(MyMessage message)  
    {  
        this.n1 = message.n1;  
        this.n2 = message.n2;  
        this.operation = message.operation;  
        this.result = message.result;  
    }  
  
    [MessageHeader]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [MessageBodyMember]  
    public double N1  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [MessageBodyMember]  
    public double N2  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [MessageBodyMember]  
    public double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
}  
```  
  
 La clase de implementación contiene el código para la operación de servicio `Calculate`. La clase `CalculateService` obtiene los operandos y el operador del mensaje de solicitud y crea un mensaje de respuesta que contiene el resultado del cálculo solicitado, tal y como se muestra en el código de ejemplo siguiente.  
  
```csharp
// Service class which implements the service contract.  
public class CalculatorService : ICalculator  
{  
    // Perform a calculation.  
  
    public MyMessage Calculate(MyMessage request)  
    {  
        MyMessage response = new MyMessage(request);  
        switch (request.Operation)  
        {  
            case "+":  
                response.Result = request.N1 + request.N2;  
                break;  
            case "-":  
                response.Result = request.N1 - request.N2;  
                break;  
            case "*":  
                response.Result = request.N1 * request.N2;  
                break;  
            case "/":  
                response.Result = request.N1 / request.N2;  
                break;  
            default:  
                response.Result = 0.0D;  
                break;  
        }  
        return response;  
    }  
}  
```  
  
 El código de cliente generado para el cliente se creó con la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) . La herramienta crea automáticamente los tipos de contratos de mensaje en el código de cliente generado si es necesario. La opción de comando `/messageContract` puede especificarse para forzar la generación de los contratos de mensaje.  
  
```console  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 El código de ejemplo siguiente muestra el cliente mediante el mensaje `MyMessage`.  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage()
                    {  
                        N1 = 100D,  
                        N2 = 15.99D,  
                        Operation = "+"  
                    };
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 Al ejecutar el ejemplo, se muestran los cálculos en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 En este punto, los mensajes definidos por el usuario personalizados han pasado entre la operación de cliente y de servicio. El contrato del mensaje definió que los operandos y los resultados estuvieran en el cuerpo del mensaje y que el operador estuviera en un encabezado del mensaje. Se puede configurar el registro de mensajes para observar esta estructura de mensaje.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
