---
title: Contrato de error
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: d8ea7010bef389b49f68c811565a641a580e230a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716952"
---
# <a name="fault-contract"></a><span data-ttu-id="17e4d-102">Contrato de error</span><span class="sxs-lookup"><span data-stu-id="17e4d-102">Fault Contract</span></span>
<span data-ttu-id="17e4d-103">El ejemplo de Contrato de error muestra cómo comunicar información de error de un servicio a un cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-103">The Fault Contract sample demonstrates how to communicate error information from a service to a client.</span></span> <span data-ttu-id="17e4d-104">El ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), con algún código adicional agregado al servicio para convertir una excepción interna en un error.</span><span class="sxs-lookup"><span data-stu-id="17e4d-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="17e4d-105">El cliente intenta realizar la división por cero para forzar una condición de error en el servicio.</span><span class="sxs-lookup"><span data-stu-id="17e4d-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17e4d-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="17e4d-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="17e4d-107">El contrato de la calculadora se ha modificado para incluir <xref:System.ServiceModel.FaultContractAttribute> como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="17e4d-108">El atributo <xref:System.ServiceModel.FaultContractAttribute> indica que la operación `Divide` puede devolver un error de tipo `MathFault`.</span><span class="sxs-lookup"><span data-stu-id="17e4d-108">The <xref:System.ServiceModel.FaultContractAttribute> attribute indicates that the `Divide` operation may return a fault of type `MathFault`.</span></span> <span data-ttu-id="17e4d-109">Un error puede ser de cualquier tipo que pueda serializarse.</span><span class="sxs-lookup"><span data-stu-id="17e4d-109">A fault can be of any type that can be serialized.</span></span> <span data-ttu-id="17e4d-110">En este caso, `MathFault` es un contrato de datos, como sigue:</span><span class="sxs-lookup"><span data-stu-id="17e4d-110">In this case, the `MathFault` is a data contract, as follows:</span></span>  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{      
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]          
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 <span data-ttu-id="17e4d-111">El método `Divide` produce una excepción <xref:System.ServiceModel.FaultException%601> cuando se fuerza una división por cero como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-111">The `Divide` method throws a <xref:System.ServiceModel.FaultException%601> exception when a divide by zero exception occurs as shown in the following sample code.</span></span> <span data-ttu-id="17e4d-112">Esta excepción produce un error que se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-112">This exception results in a fault being sent to the client.</span></span>  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 <span data-ttu-id="17e4d-113">El código de cliente fuerza un error solicitando una división por cero.</span><span class="sxs-lookup"><span data-stu-id="17e4d-113">The client code forces an error by requesting a division by zero.</span></span> <span data-ttu-id="17e4d-114">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="17e4d-115">Se puede ver la división por cero mientras se crea un informe con el error.</span><span class="sxs-lookup"><span data-stu-id="17e4d-115">You see the division by zero being reported as a fault.</span></span> <span data-ttu-id="17e4d-116">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="17e4d-117">El cliente realiza esta acción y detecta la excepción adecuada`FaultException<MathFault>`:</span><span class="sxs-lookup"><span data-stu-id="17e4d-117">The client does this by catching the appropriate `FaultException<MathFault>` exception:</span></span>  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="17e4d-118">De forma predeterminada, los detalles de excepciones inesperadas no se envían al cliente para evitar que los detalles de la implementación de servicio escapen al límite seguro del servicio.</span><span class="sxs-lookup"><span data-stu-id="17e4d-118">By default, the details of unexpected exceptions are not sent to the client to prevent details of the service implementation from escaping the secure boundary of the service.</span></span> <span data-ttu-id="17e4d-119">`FaultContract` proporciona una manera de describir errores en un contrato y de marcar determinados tipos de excepciones como adecuados para la transmisión al cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-119">`FaultContract` provides a way to describe faults in a contract and mark certain types of exceptions as appropriate for transmission to the client.</span></span> <span data-ttu-id="17e4d-120">`FaultException<T>` proporciona el mecanismo en tiempo de ejecución para enviar errores a los consumidores.</span><span class="sxs-lookup"><span data-stu-id="17e4d-120">`FaultException<T>` provides the run-time mechanism for sending faults to consumers.</span></span>  
  
 <span data-ttu-id="17e4d-121">Sin embargo, es útil para ver los detalles internos de un error del servicio al depurar.</span><span class="sxs-lookup"><span data-stu-id="17e4d-121">However, it is useful to see the internal details of a service failure when debugging.</span></span> <span data-ttu-id="17e4d-122">Para desactivar el comportamiento seguro previamente descrito, puede indicar que los detalles de cada excepción no controlada en el servidor deberían estar incluidos en el error que se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-122">To turn off the secure behavior previously described, you can indicate that the details of every unhandled exception on the server should be included in the fault that is sent to the client.</span></span> <span data-ttu-id="17e4d-123">Esto se logra estableciendo <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="17e4d-123">This is accomplished by setting <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> to `true`.</span></span> <span data-ttu-id="17e4d-124">Puede establecerlo en el código en la configuración, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e4d-124">You can either set it in code, or in configuration as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="17e4d-125">Además, el comportamiento se debe asociar al servicio estableciendo el `behaviorConfiguration` atributo del servicio en el archivo de configuración en "CalculatorServiceBehavior".</span><span class="sxs-lookup"><span data-stu-id="17e4d-125">Further, the behavior must be associated with the service by setting the `behaviorConfiguration` attribute of the service in the configuration file to "CalculatorServiceBehavior".</span></span>  
  
 <span data-ttu-id="17e4d-126">Para detectar tales errores en el cliente, se debe detectar el <xref:System.ServiceModel.FaultException> no genérico.</span><span class="sxs-lookup"><span data-stu-id="17e4d-126">To catch such faults on the client, the non-generic <xref:System.ServiceModel.FaultException> must be caught.</span></span>  
  
 <span data-ttu-id="17e4d-127">Este comportamiento se debería utilizar solo para los propósitos de depuración y no estar habilitado nunca en producción.</span><span class="sxs-lookup"><span data-stu-id="17e4d-127">This behavior should only be used for debugging purposes and should never be enabled in production.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="17e4d-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="17e4d-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="17e4d-129">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17e4d-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="17e4d-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17e4d-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="17e4d-131">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="17e4d-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="17e4d-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="17e4d-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="17e4d-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="17e4d-133">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="17e4d-134">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17e4d-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="17e4d-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="17e4d-135">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
