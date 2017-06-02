---
title: "Contrato de mensaje predeterminado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Contrato de mensaje"
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Contrato de mensaje predeterminado
El ejemplo de contrato de mensaje predeterminado muestra un servicio donde un mensaje personalizado definido por el usuario se pasa a las operaciones de servicio y desde ellas.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa una interfaz de calculadora como un servicio con tipos.En lugar de las operaciones de servicio individuales para la suma, resta, multiplicación y división utilizadas en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md), este ejemplo pasa un mensaje personalizado que contiene a los operandos y el operador, y devuelve el resultado del cálculo aritmético.  
  
 El cliente es un programa de la consola \(.exe\) e Internet Information Services \(IIS\) hospeda la biblioteca de servicio.La actividad del cliente es visible en la ventana de la consola.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En el servicio, se define una única operación de servicio que acepta y devuelve mensajes personalizados de tipo `MyMessage`.Aunque en este ejemplo los mensajes de solicitud y respuesta son del mismo tipo, podrían ser desde luego contratos de mensaje diferentes si fuera necesario.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
  
```  
  
 Se define el mensaje personalizado `MyMessage` en una clase anotada con los atributos <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>.Sólo se usa el tercer constructor en este ejemplo.Utilizar los contratos de mensaje le permite ejercer control completo sobre el mensaje SOAP.En este ejemplo, el atributo <xref:System.ServiceModel.MessageHeaderAttribute> se utiliza para colocar `Operation` en un encabezado SOAP.Los operandos `N1`, `N2` y `Result` aparecen dentro del cuerpo de SOAP porque tienen el atributo <xref:System.ServiceModel.MessageBodyMemberAttribute> aplicado.  
  
```  
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
  
 La clase de implementación contiene el código para la operación de servicio `Calculate`.La clase `CalculateService` obtiene los operandos y el operador del mensaje de solicitud y crea un mensaje de respuesta que contiene el resultado del cálculo solicitado, tal y como se muestra en el código de ejemplo siguiente.  
  
```  
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
  
 El código de cliente generado para el cliente se creó con la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).La herramienta crea automáticamente los tipos de contratos de mensaje en el código de cliente generado si es necesario.La opción de comando `/messageContract` puede especificarse para forzar la generación de los contratos de mensaje.  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 El código de ejemplo siguiente muestra el cliente mediante el mensaje `MyMessage`.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage();  
request.N1 = 100D;  
request.N2 = 15.99D;  
request.Operation = "+";  
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 Al ejecutar el ejemplo, se muestran los cálculos en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
  
```  
  
 En este punto, los mensajes definidos por el usuario personalizados han pasado entre la operación de cliente y de servicio.El contrato del mensaje definió que los operandos y los resultados estuvieran en el cuerpo del mensaje y que el operador estuviera en un encabezado del mensaje.Se puede configurar el registro de mensajes para observar esta estructura de mensaje.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
  
## Vea también