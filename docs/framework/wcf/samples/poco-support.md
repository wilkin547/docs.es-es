---
description: 'Más información acerca de: compatibilidad POCO'
title: Compatibilidad con POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: 8d44e7a3ebffc6c460a735587ca56990953b2d9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793186"
---
# <a name="poco-support"></a><span data-ttu-id="84dec-103">Compatibilidad con POCO</span><span class="sxs-lookup"><span data-stu-id="84dec-103">POCO Support</span></span>

<span data-ttu-id="84dec-104">En este ejemplo se muestra la compatibilidad para la serialización de los tipos sin marca; es decir, tipos a los que no se han aplicado atributos de serialización, a veces conocidos como tipos de objetos CLR antiguos sin formato (POCO).</span><span class="sxs-lookup"><span data-stu-id="84dec-104">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="84dec-105"><xref:System.Runtime.Serialization.DataContractSerializer>Deduce un contrato de datos para todos los tipos públicos no marcados que tienen un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="84dec-105">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a parameterless constructor.</span></span> <span data-ttu-id="84dec-106">Los contratos de datos le permiten pasar los datos estructurados hacia y desde los servicios.</span><span class="sxs-lookup"><span data-stu-id="84dec-106">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="84dec-107">Para obtener más información sobre los tipos no marcados, vea [tipos serializables](../feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="84dec-107">For more information about unmarked types, see [Serializable Types](../feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="84dec-108">Este ejemplo se basa en el [Introducción](getting-started-sample.md), pero utiliza números complejos en lugar de tipos numéricos primitivos.</span><span class="sxs-lookup"><span data-stu-id="84dec-108">This sample is based on the [Getting Started](getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="84dec-109">También es similar al ejemplo de [contrato de datos básico](basic-data-contract.md) , con la excepción de que <xref:System.Runtime.Serialization.DataContractAttribute> <xref:System.Runtime.Serialization.DataMemberAttribute> no se utilizan los atributos y.</span><span class="sxs-lookup"><span data-stu-id="84dec-109">It is also similar to the [Basic Data Contract](basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="84dec-110">El cliente es una aplicación de consola (.exe) e Internet Information Services (IIS) hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="84dec-110">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84dec-111">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="84dec-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="84dec-112">La clase `ComplexNumber` se utiliza en la clase `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="84dec-112">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="84dec-113">El tipo `ComplexNumber` no tiene los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="84dec-113">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="84dec-114">De manera predeterminada, se serializan todas las propiedades y campos públicos.</span><span class="sxs-lookup"><span data-stu-id="84dec-114">By default, all public properties and fields are serialized.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="84dec-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="84dec-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="84dec-116">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dec-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="84dec-117">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dec-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="84dec-118">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dec-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="84dec-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="84dec-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84dec-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="84dec-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="84dec-121">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="84dec-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84dec-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="84dec-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="84dec-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="84dec-123">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="84dec-124">Tipos serializables</span><span class="sxs-lookup"><span data-stu-id="84dec-124">Serializable Types</span></span>](../feature-details/serializable-types.md)
