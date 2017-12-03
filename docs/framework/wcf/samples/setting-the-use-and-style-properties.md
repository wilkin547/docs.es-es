---
title: Establecimiento del uso y estilo de las propiedades
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6a8e4b990c7ae9815c8792c0be456463b10660b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="setting-the-use-and-style-properties"></a><span data-ttu-id="58f9a-102">Establecimiento del uso y estilo de las propiedades</span><span class="sxs-lookup"><span data-stu-id="58f9a-102">Setting the Use and Style Properties</span></span>
<span data-ttu-id="58f9a-103">En este ejemplo se muestra cómo se utiliza el uso y las propiedades de estilo en <xref:System.ServiceModel.XmlSerializerFormatAttribute> y en <xref:System.ServiceModel.DataContractFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="58f9a-103">This sample demonstrates how to use the Use and Style properties on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> and the <xref:System.ServiceModel.DataContractFormatAttribute>.</span></span> <span data-ttu-id="58f9a-104">Estas propiedades afectan a la forma en que se ha dado formato a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="58f9a-104">These properties affect how messages are formatted.</span></span> <span data-ttu-id="58f9a-105">De forma predeterminada, se da formato al cuerpo del mensaje con el estilo establecido en <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="58f9a-105">By default, the message body is formatted with the style set to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span> <span data-ttu-id="58f9a-106">Esta configuración se puede especificar en el nivel del contrato de servicios o en el nivel del contrato de operación.</span><span class="sxs-lookup"><span data-stu-id="58f9a-106">These settings can be specified at either the service contract level or the operation contract level.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58f9a-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="58f9a-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="58f9a-108">La propiedad de estilo <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> determina cómo se da formato a los metadatos de WSDL para el servicio.</span><span class="sxs-lookup"><span data-stu-id="58f9a-108">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> style property determines how the WSDL metadata for the service is formatted.</span></span> <span data-ttu-id="58f9a-109">Los valores posibles son <xref:System.ServiceModel.OperationFormatStyle.Document>, y <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span><span class="sxs-lookup"><span data-stu-id="58f9a-109">Possible values are <xref:System.ServiceModel.OperationFormatStyle.Document>, and <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span></span> <span data-ttu-id="58f9a-110">RPC significa que la representación de WSDL de los mensajes intercambiados para una operación contiene parámetros como si fuera una llamada de procedimiento remoto.</span><span class="sxs-lookup"><span data-stu-id="58f9a-110">RPC means that the WSDL representation of messages exchanged for an operation contains parameters as if it were a remote procedure call.</span></span> <span data-ttu-id="58f9a-111">A continuación se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58f9a-111">The following is an example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="n1" type="xsd:double"/>  
  <wsdl:part name="n2" type="xsd:double"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="58f9a-112">Establecer el estilo en <xref:System.ServiceModel.OperationFormatStyle.Document> quiere decir que la representación de WSDL contiene un elemento único que representa el documento que se intercambia para una operación tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="58f9a-112">Setting the style to <xref:System.ServiceModel.OperationFormatStyle.Document> means that the WSDL representation contains a single element that represents the document that is exchanged for an operation as shown in the following example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="parameters" element="tns:Add"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="58f9a-113">La propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> determina el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="58f9a-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property determines the format of the message.</span></span> <span data-ttu-id="58f9a-114">Los valores posibles son <xref:System.ServiceModel.OperationFormatUse.Literal> y <xref:System.ServiceModel.OperationFormatUse.Encoded>; el valor predeterminado es <xref:System.ServiceModel.OperationFormatUse.Literal>.</span><span class="sxs-lookup"><span data-stu-id="58f9a-114">Possible values are <xref:System.ServiceModel.OperationFormatUse.Literal> and <xref:System.ServiceModel.OperationFormatUse.Encoded>; the default value is <xref:System.ServiceModel.OperationFormatUse.Literal>.</span></span> <span data-ttu-id="58f9a-115">Literal significa que el mensaje es una instancia literal del esquema en WSDL, tal y como se muestra en el siguiente ejemplo de documento/literal.</span><span class="sxs-lookup"><span data-stu-id="58f9a-115">Literal means that the message is a literal instance of the schema in the WSDL as shown in the following Document/ Literal example.</span></span>  
  
```xml  
<Add xmlns="http://Microsoft.ServiceModel.Samples">  
  <n1>100</n1>  
  <n2>15.99</n2>  
</Add>  
```  
  
 <span data-ttu-id="58f9a-116">Codificado significa que los esquemas en WSDL son especificaciones abstractas que se codifican según las reglas situadas en la sección 5 de SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="58f9a-116">Encoded means that the schemas in the WSDL are abstract specifications that are encoded according to the rules found in SOAP 1.1 section 5.</span></span> <span data-ttu-id="58f9a-117">El siguiente es un ejemplo de RPC/Encoded.</span><span class="sxs-lookup"><span data-stu-id="58f9a-117">The following is an RPC/Encoded example.</span></span>  
  
```xml  
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">  
  <n1 xsi:type="xsd:double" xmlns="">100</n1>  
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>  
</q1:Add>  
```  
  
 <span data-ttu-id="58f9a-118">El WS-I Basic Profile 1.0 prohibe el uso de <xref:System.ServiceModel.OperationFormatUse.Encoded> y se debería utilizar solo cuando los servicios heredados así lo requieran.</span><span class="sxs-lookup"><span data-stu-id="58f9a-118">The WS-I Basic Profile 1.0 prohibits the use of <xref:System.ServiceModel.OperationFormatUse.Encoded> and you should only use it when required by legacy services.</span></span> <span data-ttu-id="58f9a-119">El formato de mensaje `Encoded` solo está disponible al utilizar XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="58f9a-119">The `Encoded` message format is only available when using the XmlSerializer.</span></span>  
  
 <span data-ttu-id="58f9a-120">Para que pueda ver los mensajes que se envían y reciben, este ejemplo se basa en el [seguimiento y registro de mensajes](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="58f9a-120">To allow you to see the messages being sent and received, this sample is based on the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span> <span data-ttu-id="58f9a-121">La configuración de servicio y código fuente se han modificado para habilitar y utilizar el seguimiento y registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="58f9a-121">The service configuration and source code have been modified to enable and utilize tracing and message logging.</span></span> <span data-ttu-id="58f9a-122">Además, el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> se ha configurado sin la seguridad, por lo que se pueden ver los mensajes registrados en un formato sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="58f9a-122">In addition, the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> has been configured without security, so the logged messages can be viewed in an unencrypted format.</span></span> <span data-ttu-id="58f9a-123">Deben ver los registros de seguimiento resultante (System.ServiceModel.e2e y Message.log) mediante el [herramienta Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="58f9a-123">The resulting trace logs (System.ServiceModel.e2e and Message.log) should be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="58f9a-124">Los rastros se configuran para ser creados en la carpeta C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="58f9a-124">The traces are configured to be created in the C:\LOGS folder.</span></span> <span data-ttu-id="58f9a-125">Cree la carpeta antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="58f9a-125">Create the folder before running the sample.</span></span> <span data-ttu-id="58f9a-126">Para ver el contenido del mensaje en la herramienta de Visor de seguimiento, seleccione **mensajes** en la izquierda y los paneles de la derecha de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="58f9a-126">To view message contents in the Trace Viewer tool, select **Messages** in both the left and the right panes of the tool.</span></span>  
  
 <span data-ttu-id="58f9a-127">El código siguiente muestra el contrato de servicios con la propiedad <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> establecida en <xref:System.ServiceModel.OperationFormatUse> y el formato del cuerpo del mensaje cambiados del <xref:System.ServiceModel.OperationFormatStyle> predeterminado a <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="58f9a-127">The following code shows the service contract with the <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property set to <xref:System.ServiceModel.OperationFormatUse> and the format of the message body changed from the default <xref:System.ServiceModel.OperationFormatStyle> to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
XmlSerializerFormat(Style = OperationFormatStyle.Rpc,   
                                 Use = OperationFormatUse.Encoded)]  
public interface IUseAndStyleCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="58f9a-128">Para ver la diferencia entre el <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> diferente y los valores <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, modifíquelos en el servicio, regenere el cliente, ejecute el ejemplo y examine el archivo c:\logs\message.logs con la herramienta Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="58f9a-128">To see the difference between the different <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> and <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> settings, modify them in the service, regenerate the client, run the sample, and examine the c:\logs\message.logs file with the Service Trace Viewer tool.</span></span> <span data-ttu-id="58f9a-129">Observe también el impacto en los metadatos viendo http://localhost/ServiceModelSamples/service.svc? wsdl.</span><span class="sxs-lookup"><span data-stu-id="58f9a-129">Also observe the impact on the metadata by viewing http://localhost/ServiceModelSamples/service.svc?wsdl.</span></span> <span data-ttu-id="58f9a-130">Los metadatos para los servicios se irrumpen normalmente en varias páginas.</span><span class="sxs-lookup"><span data-stu-id="58f9a-130">The metadata for services is typically broken up into multiple pages.</span></span> <span data-ttu-id="58f9a-131">La página wsdl principal contiene los enlaces de WSDL, pero vea http://localhost/ServiceModelSamples/service.svc de la vista? wsdl=wsdl0 para observar las definiciones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="58f9a-131">The main wsdl page contains the WSDL bindings, but view http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0 to observe the message definitions.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="58f9a-132">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="58f9a-132">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="58f9a-133">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58f9a-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="58f9a-134">Cree un directorio C:\LOGS para registrar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="58f9a-134">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="58f9a-135">Proporcione a los usuarios permisos de escritura de servicio de red para este directorio.</span><span class="sxs-lookup"><span data-stu-id="58f9a-135">Give the user Network Service write permissions for this directory.</span></span>  
  
3.  <span data-ttu-id="58f9a-136">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58f9a-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="58f9a-137">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="58f9a-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58f9a-138">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="58f9a-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58f9a-139">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="58f9a-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58f9a-140">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58f9a-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58f9a-141">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="58f9a-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`  
  
## <a name="see-also"></a><span data-ttu-id="58f9a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="58f9a-142">See Also</span></span>
