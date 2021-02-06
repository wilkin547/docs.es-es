---
description: 'Más información acerca de: contrato de mensaje predeterminado'
title: Contrato de mensaje predeterminado
ms.date: 03/30/2017
helpviewer_keywords:
- Message Contract
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
ms.openlocfilehash: 3587f6ce81e085a4915af8162f8d76aed30bf8df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632092"
---
# <a name="default-message-contract"></a><span data-ttu-id="5296d-103">Contrato de mensaje predeterminado</span><span class="sxs-lookup"><span data-stu-id="5296d-103">Default Message Contract</span></span>

<span data-ttu-id="5296d-104">El ejemplo de contrato de mensaje predeterminado muestra un servicio donde un mensaje personalizado definido por el usuario se pasa a las operaciones de servicio y desde ellas.</span><span class="sxs-lookup"><span data-stu-id="5296d-104">The Default Message Contract sample demonstrates a service where a custom user-defined message is passed to and from service operations.</span></span> <span data-ttu-id="5296d-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa una interfaz de calculadora como un servicio con tipo.</span><span class="sxs-lookup"><span data-stu-id="5296d-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator interface as a typed service.</span></span> <span data-ttu-id="5296d-106">En lugar de las operaciones de servicio individuales para la suma, resta, multiplicación y división utilizadas en el [Introducción](getting-started-sample.md), este ejemplo pasa un mensaje personalizado que contiene los operandos y el operador, y devuelve el resultado del cálculo aritmético.</span><span class="sxs-lookup"><span data-stu-id="5296d-106">Instead of the individual service operations for addition, subtraction, multiplication, and division used in the [Getting Started](getting-started-sample.md), this sample passes a custom message that contains both the operands and the operator, and returns the result of the arithmetic calculation.</span></span>  
  
 <span data-ttu-id="5296d-107">El cliente es un programa de la consola (.exe) e Internet Information Services (IIS) hospeda la biblioteca de servicio.</span><span class="sxs-lookup"><span data-stu-id="5296d-107">The client is a console program (.exe) and the service library (.dll) is hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="5296d-108">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="5296d-108">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5296d-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="5296d-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="5296d-110">En el servicio, se define una única operación de servicio que acepta y devuelve mensajes personalizados de tipo `MyMessage`.</span><span class="sxs-lookup"><span data-stu-id="5296d-110">In the service, a single service operation is defined that accepts and returns custom messages of type `MyMessage`.</span></span> <span data-ttu-id="5296d-111">Aunque en este ejemplo los mensajes de solicitud y respuesta son del mismo tipo, podrían ser desde luego contratos de mensaje diferentes si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="5296d-111">Although in this sample the request and response messages are of the same type, they could of course be different message contracts if necessary.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
```  
  
 <span data-ttu-id="5296d-112">Se define el mensaje personalizado `MyMessage` en una clase anotada con los atributos <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> y <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5296d-112">The custom message `MyMessage` is defined in a class annotated with <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="5296d-113">Sólo se usa el tercer constructor en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5296d-113">Only the third constructor is used in this sample.</span></span> <span data-ttu-id="5296d-114">Utilizar los contratos de mensaje le permite ejercer control completo sobre el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="5296d-114">Using message contracts allows you to exercise full control over the SOAP message.</span></span> <span data-ttu-id="5296d-115">En este ejemplo, el atributo <xref:System.ServiceModel.MessageHeaderAttribute> se utiliza para colocar `Operation` en un encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="5296d-115">In this sample, the <xref:System.ServiceModel.MessageHeaderAttribute> attribute is used to put `Operation` in a SOAP header.</span></span> <span data-ttu-id="5296d-116">Los operandos `N1`, `N2` y `Result` aparecen dentro del cuerpo de SOAP porque tienen el atributo <xref:System.ServiceModel.MessageBodyMemberAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="5296d-116">The operands `N1`, `N2` and the `Result` appear within the SOAP body because they have the <xref:System.ServiceModel.MessageBodyMemberAttribute> attribute applied.</span></span>  
  
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
  
 <span data-ttu-id="5296d-117">La clase de implementación contiene el código para la operación de servicio `Calculate`.</span><span class="sxs-lookup"><span data-stu-id="5296d-117">The implementation class contains the code for the `Calculate` service operation.</span></span> <span data-ttu-id="5296d-118">La clase `CalculateService` obtiene los operandos y el operador del mensaje de solicitud y crea un mensaje de respuesta que contiene el resultado del cálculo solicitado, tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5296d-118">The `CalculateService` class obtains the operands and operator from the request message and creates a response message that contains the result of the requested calculation, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="5296d-119">El código de cliente generado para el cliente se creó con la herramienta de [utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="5296d-119">The generated client code for the client was created with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span> <span data-ttu-id="5296d-120">La herramienta crea automáticamente los tipos de contratos de mensaje en el código de cliente generado si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5296d-120">The tool automatically creates message contract types in the generated client code if necessary.</span></span> <span data-ttu-id="5296d-121">La opción de comando `/messageContract` puede especificarse para forzar la generación de los contratos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5296d-121">The `/messageContract` command option may be specified to force the generation of message contracts.</span></span>  
  
```console  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="5296d-122">El código de ejemplo siguiente muestra el cliente mediante el mensaje `MyMessage`.</span><span class="sxs-lookup"><span data-stu-id="5296d-122">The following sample code demonstrates the client using the `MyMessage` message.</span></span>  
  
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
  
 <span data-ttu-id="5296d-123">Al ejecutar el ejemplo, se muestran los cálculos en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="5296d-123">When you run the sample, the calculations are displayed in the client console window.</span></span> <span data-ttu-id="5296d-124">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="5296d-124">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="5296d-125">En este punto, los mensajes definidos por el usuario personalizados han pasado entre la operación de cliente y de servicio.</span><span class="sxs-lookup"><span data-stu-id="5296d-125">At this point, custom user-defined messages have passed between the client and the service operation.</span></span> <span data-ttu-id="5296d-126">El contrato del mensaje definió que los operandos y los resultados estuvieran en el cuerpo del mensaje y que el operador estuviera en un encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5296d-126">The message contract defined that the operands and results were in the message body and that the operator was in a message header.</span></span> <span data-ttu-id="5296d-127">Se puede configurar el registro de mensajes para observar esta estructura de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5296d-127">Message logging can be configured to observe this message structure.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5296d-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5296d-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5296d-129">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5296d-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5296d-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5296d-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="5296d-131">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5296d-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5296d-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5296d-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5296d-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5296d-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="5296d-134">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5296d-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5296d-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5296d-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
