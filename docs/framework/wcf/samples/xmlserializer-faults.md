---
title: Errores de XmlSerializer
ms.date: 03/30/2017
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
ms.openlocfilehash: adb14fdb45aa71bbaf4585cbfba55059df7cddf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183150"
---
# <a name="xmlserializer-faults"></a><span data-ttu-id="080b5-102">Errores de XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="080b5-102">XmlSerializer Faults</span></span>
<span data-ttu-id="080b5-103">El ejemplo de contrato de error <xref:System.Xml.Serialization.XmlSerializer> muestra cómo comunicar información de error de un servicio a un cliente mediante <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="080b5-103">The <xref:System.Xml.Serialization.XmlSerializer> fault contract sample demonstrates how to communicate error information from a service to a client using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="080b5-104">El ejemplo se basa en [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), con código adicional agregado al servicio para convertir una excepción interna en un error.</span><span class="sxs-lookup"><span data-stu-id="080b5-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="080b5-105">El cliente intenta realizar la división por cero para forzar una condición de error en el servicio.</span><span class="sxs-lookup"><span data-stu-id="080b5-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="080b5-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="080b5-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="080b5-107">El contrato de la calculadora se ha modificado para incluir <xref:System.ServiceModel.FaultContractAttribute> como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="080b5-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span> <span data-ttu-id="080b5-108">Asimismo, <xref:System.ServiceModel.XmlSerializerFormatAttribute> se utiliza para habilitar la serialización mediante <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="080b5-108">Also, the <xref:System.ServiceModel.XmlSerializerFormatAttribute> is used to enable serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="080b5-109">La propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> se establece en `true` en este atributo, lo que indica al serializador que utilice <xref:System.Xml.Serialization.XmlSerializer> para leer y escribir los errores.</span><span class="sxs-lookup"><span data-stu-id="080b5-109">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> property is set to `true` on this attribute, which instructs the serializer to use the <xref:System.Xml.Serialization.XmlSerializer> for reading and writing faults.</span></span>  
  
```csharp
[XmlSerializerFormat(SupportFaults=true)]  
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
  
 <span data-ttu-id="080b5-110">Al generar código para el proxy de cliente, debe aplicar la marca **/UseSerializerForFaults** a [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="080b5-110">When generating code for the client proxy, you must apply the **/UseSerializerForFaults** flag to [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="080b5-111">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="080b5-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="080b5-112">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="080b5-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="080b5-113">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="080b5-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="080b5-114">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="080b5-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="080b5-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="080b5-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="080b5-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="080b5-116">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="080b5-117">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="080b5-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="080b5-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="080b5-118">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a><span data-ttu-id="080b5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="080b5-119">See also</span></span>

- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
