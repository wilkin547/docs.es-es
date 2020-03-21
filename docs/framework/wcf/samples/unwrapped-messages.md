---
title: Mensajes desajustados
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: 81592910d8530cea2df5ec1fd8a8b1145350ef78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143738"
---
# <a name="unwrapped-messages"></a><span data-ttu-id="747d3-102">Mensajes desajustados</span><span class="sxs-lookup"><span data-stu-id="747d3-102">Unwrapped Messages</span></span>
<span data-ttu-id="747d3-103">Este ejemplo muestra mensajes desajustados.</span><span class="sxs-lookup"><span data-stu-id="747d3-103">This sample demonstrates unwrapped messages.</span></span> <span data-ttu-id="747d3-104">De forma predeterminada, se da formato al cuerpo del mensaje de manera que se ajusten los parámetros a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="747d3-104">By default, the message body is formatted such that the parameters to a service operation are wrapped.</span></span> <span data-ttu-id="747d3-105">El ejemplo siguiente muestra un mensaje de solicitud `Add` al servicio `ICalculator` en modo ajustado.</span><span class="sxs-lookup"><span data-stu-id="747d3-105">The following sample shows an `Add` request message to the `ICalculator` service in wrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="747d3-106">El elemento `<Add>` en el cuerpo del mensaje ajusta los parámetros `n1` y `n2`.</span><span class="sxs-lookup"><span data-stu-id="747d3-106">The `<Add>` element in the message body wraps the `n1` and `n2` parameters.</span></span> <span data-ttu-id="747d3-107">En contraste, el ejemplo siguiente muestra el mensaje equivalente en el modo desajustado.</span><span class="sxs-lookup"><span data-stu-id="747d3-107">In contrast, the following sample shows the equivalent message in the unwrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 <span data-ttu-id="747d3-108">El mensaje desajustado no ajusta los parámetros `n1` y `n2` en un elemento contenedor, sino que son elementos secundarios directos del elemento del cuerpo de SOAP.</span><span class="sxs-lookup"><span data-stu-id="747d3-108">The unwrapped message does not wrap the `n1` and `n2` parameters in a containing element, they are direct children of the soap body element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="747d3-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="747d3-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="747d3-110">En este ejemplo, se crea un mensaje desajustado aplicando <xref:System.ServiceModel.MessageContractAttribute> al tipo de parámetro de operación de servicio y devuelve el tipo de valor tal y como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="747d3-110">In this sample, an unwrapped message is created by applying the <xref:System.ServiceModel.MessageContractAttribute> to the service operation parameter type and return value type as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 <span data-ttu-id="747d3-111">Para permitirle ver los mensajes que se envían y se reciben, este ejemplo utiliza la traza.</span><span class="sxs-lookup"><span data-stu-id="747d3-111">To allow you to see the messages being sent and received, this sample uses tracing.</span></span> <span data-ttu-id="747d3-112">Además, se ha configurado <xref:System.ServiceModel.WSHttpBinding> sin seguridad para reducir el número de mensajes que registra.</span><span class="sxs-lookup"><span data-stu-id="747d3-112">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, to reduce the number of messages it logs.</span></span>  
  
 <span data-ttu-id="747d3-113">El registro de seguimiento resultante (c:-logs-Message.log) se puede ver mediante la [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="747d3-113">The resulting trace log (c:\logs\Message.log) can be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="747d3-114">Para ver el contenido del mensaje, seleccione **Mensajes** en los paneles izquierdo y derecho de la herramienta Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="747d3-114">To view message contents, select **Messages** in both the left and the right panes of the Service Trace Viewer tool.</span></span> <span data-ttu-id="747d3-115">Los registros de traza en este ejemplo se configuran para que se generen en la carpeta C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="747d3-115">Trace logs in this sample are configured to be generated into the C:\LOGS folder.</span></span> <span data-ttu-id="747d3-116">Cree esta carpeta antes de ejecutar el ejemplo y proporcione al usuario permisos de escritura para el servicio de red correspondiente a este directorio.</span><span class="sxs-lookup"><span data-stu-id="747d3-116">Create this folder before running the sample and give the user Network Service write permissions for this directory.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="747d3-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="747d3-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="747d3-118">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="747d3-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="747d3-119">Cree un directorio C:\LOGS para registrar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="747d3-119">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="747d3-120">Proporcione a los usuarios permisos de escritura de servicio de red para este directorio.</span><span class="sxs-lookup"><span data-stu-id="747d3-120">Give the user Network Service write permissions for this directory.</span></span>  
  
3. <span data-ttu-id="747d3-121">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="747d3-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="747d3-122">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="747d3-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="747d3-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="747d3-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="747d3-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="747d3-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="747d3-125">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="747d3-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="747d3-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="747d3-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
