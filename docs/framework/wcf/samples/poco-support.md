---
title: Compatibilidad con POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: 2962fa8a9eb824bbfbbb2f1e9347f8988b50ddcd
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716544"
---
# <a name="poco-support"></a><span data-ttu-id="58ac2-102">Compatibilidad con POCO</span><span class="sxs-lookup"><span data-stu-id="58ac2-102">POCO Support</span></span>
<span data-ttu-id="58ac2-103">En este ejemplo se muestra la compatibilidad para la serialización de los tipos sin marca; es decir, tipos a los que no se han aplicado atributos de serialización, a veces conocidos como tipos de objetos CLR antiguos sin formato (POCO).</span><span class="sxs-lookup"><span data-stu-id="58ac2-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="58ac2-104">El <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos para todos los tipos públicos no marcados que tienen un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="58ac2-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a parameterless constructor.</span></span> <span data-ttu-id="58ac2-105">Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios.</span><span class="sxs-lookup"><span data-stu-id="58ac2-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="58ac2-106">Para obtener más información sobre los tipos no marcados, vea [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="58ac2-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="58ac2-107">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), pero utiliza números complejos en lugar de tipos numéricos primitivos.</span><span class="sxs-lookup"><span data-stu-id="58ac2-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="58ac2-108">También es similar al ejemplo de [contrato de datos básico](../../../../docs/framework/wcf/samples/basic-data-contract.md) , salvo que no se utilizan los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="58ac2-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="58ac2-109">El cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="58ac2-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58ac2-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="58ac2-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="58ac2-111">La clase `ComplexNumber` se utiliza en la clase `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="58ac2-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="58ac2-112">El tipo `ComplexNumber` no tiene los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58ac2-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="58ac2-113">De manera predeterminada, se serializan todas las propiedades y campos públicos.</span><span class="sxs-lookup"><span data-stu-id="58ac2-113">By default, all public properties and fields are serialized.</span></span>  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="58ac2-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="58ac2-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="58ac2-115">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58ac2-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="58ac2-116">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58ac2-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="58ac2-117">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58ac2-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="58ac2-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="58ac2-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58ac2-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="58ac2-119">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="58ac2-120">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58ac2-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58ac2-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="58ac2-121">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="58ac2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="58ac2-122">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="58ac2-123">Tipos serializables</span><span class="sxs-lookup"><span data-stu-id="58ac2-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
