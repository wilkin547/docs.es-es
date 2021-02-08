---
description: 'Más información acerca de: contrato de datos básico'
title: Contrato de datos básico
ms.date: 03/30/2017
helpviewer_keywords:
- Data Contract
ms.assetid: b124e9e0-cb73-4ae0-b9c3-e6cdf5eced98
ms.openlocfilehash: 332b9325e87c91be70e1ddd708902c4cef3777b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778872"
---
# <a name="basic-data-contract"></a><span data-ttu-id="ac892-103">Contrato de datos básico</span><span class="sxs-lookup"><span data-stu-id="ac892-103">Basic Data Contract</span></span>

<span data-ttu-id="ac892-104">Este ejemplo muestra cómo implementar un contrato de datos.</span><span class="sxs-lookup"><span data-stu-id="ac892-104">This sample demonstrates how to implement a data contract.</span></span> <span data-ttu-id="ac892-105">Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios.</span><span class="sxs-lookup"><span data-stu-id="ac892-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="ac892-106">Este ejemplo se basa en el [Introducción](getting-started-sample.md) pero utiliza números complejos en lugar de tipos numéricos básicos.</span><span class="sxs-lookup"><span data-stu-id="ac892-106">This sample is based on the [Getting Started](getting-started-sample.md) but uses complex numbers instead of basic numeric types.</span></span>

<span data-ttu-id="ac892-107">En este ejemplo, el cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="ac892-107">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>

> [!NOTE]
> <span data-ttu-id="ac892-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ac892-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="ac892-109">El contrato de servicios para este servicio utiliza números complejos, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac892-109">The service contract for this service uses complex numbers, as shown in the following sample code.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);
    [OperationContract]
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);
}
```

 <span data-ttu-id="ac892-110"><xref:System.Runtime.Serialization.DataContractAttribute> y los atributos <xref:System.Runtime.Serialization.DataMemberAttribute> se han aplicado a la definición de la clase `ComplexNumber` para indicar qué campos de la clase se pueden pasar a través de la conexión entre el cliente y el servicio, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac892-110">The <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes have been applied to the definition of the `ComplexNumber` class to indicate which fields of the class can be passed over the wire between the client and the service, as shown in the following sample code.</span></span>

```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public class ComplexNumber
{
    [DataMember]
    public double Real = 0.0D;
    [DataMember]
    public double Imaginary = 0.0D;

    public ComplexNumber(double real, double imaginary)
    {
        this.Real = real;
        this.Imaginary = imaginary;
    }
}
```

<span data-ttu-id="ac892-111">La implementación del servicio calcula y devuelve los resultados adecuados, aceptando y devolviendo números del tipo `ComplexNumber`.</span><span class="sxs-lookup"><span data-stu-id="ac892-111">The service implementation calculates and returns the appropriate result, accepting and returning numbers of the `ComplexNumber` type.</span></span>

```csharp
// This is the service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +
                                                      n2.Imaginary);
    }

    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real - n2.Real, n1.Imaginary -
                                                     n2.Imaginary);
    }
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)
    {
        double real1 = n1.Real * n2.Real;
        double imaginary1 = n1.Real * n2.Imaginary;
        double imaginary2 = n2.Real * n1.Imaginary;
        double real2 = n1.Imaginary * n2.Imaginary * -1;
        return new ComplexNumber(real1 + real2, imaginary1 +
                                                 imaginary2);
    }

    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)
    {
         ComplexNumber conjugate =
              new ComplexNumber(n2.Real, -1*n2.Imaginary);
         ComplexNumber numerator = Multiply(n1, conjugate);
         ComplexNumber denominator = Multiply(n2, conjugate);
         return new ComplexNumber(numerator.Real / denominator.Real,
                                               numerator.Imaginary);
    }
}
```

<span data-ttu-id="ac892-112">La implementación del cliente también utiliza números complejos.</span><span class="sxs-lookup"><span data-stu-id="ac892-112">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="ac892-113">El contrato de servicio y el contrato de datos se definen en el archivo de código fuente generatedClient.cs, generado por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac892-113">Both the service contract and the data contract are defined in the source file generatedClient.cs, which is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span>

```csharp
// Create a client.
DataContractCalculatorClient client = new DataContractCalculatorClient();
// Call the Add service operation.
ComplexNumber value1 = new ComplexNumber()
                    {
                        Real = 1,
                        Imaginary = 2
                    };
ComplexNumber value2 = new ComplexNumber()
                    {
                        Real = 3,
                        Imaginary = 4
                    };
ComplexNumber result = proxy.Add(value1, value2);
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",
      value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,
      result.Real, result.Imaginary);
    …
}
```

<span data-ttu-id="ac892-114">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac892-114">When you run the sample, the requests and responses of the operation are displayed in the client console window.</span></span> <span data-ttu-id="ac892-115">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac892-115">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(1 + 2i, 3 + 4i) = 4 + 6i
Subtract(1 + 2i, 3 + 4i) = -2 + -2i
Multiply(2 + 3i, 4 + 7i) = -13 + 26i
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac892-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac892-116">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ac892-117">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac892-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="ac892-118">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac892-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="ac892-119">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac892-119">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac892-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ac892-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac892-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ac892-121">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ac892-122">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ac892-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac892-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ac892-123">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`
