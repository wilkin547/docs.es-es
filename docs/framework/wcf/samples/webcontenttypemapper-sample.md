---
title: Ejemplo de WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 550e763d30a7fa503f6500dcaa8f9b77ea499bca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283268"
---
# <a name="webcontenttypemapper-sample"></a><span data-ttu-id="54b23-102">Ejemplo de WebContentTypeMapper</span><span class="sxs-lookup"><span data-stu-id="54b23-102">WebContentTypeMapper Sample</span></span>

<span data-ttu-id="54b23-103">Este ejemplo muestra cómo asignar los nuevos tipos de contenido a los formatos de cuerpo de mensaje de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="54b23-103">This sample demonstrates how to map new content types to Windows Communication Foundation (WCF) message body formats.</span></span>  
  
 <span data-ttu-id="54b23-104">El <xref:System.ServiceModel.Description.WebHttpEndpoint> elemento se conecta en el codificador de mensajes Web, que permite a WCF recibir mensajes binarios JSON, XML o sin formato en el mismo punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="54b23-104">The <xref:System.ServiceModel.Description.WebHttpEndpoint> element plugs in the Web message encoder, which allows WCF to receive JSON, XML, or raw binary messages at the same endpoint.</span></span> <span data-ttu-id="54b23-105">El codificador determina el formato del cuerpo del mensaje examinando el tipo de contenido del Http de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="54b23-105">The encoder determines the body format of the message by looking at the HTTP content-type of the request.</span></span> <span data-ttu-id="54b23-106">Este ejemplo incluye la clase <xref:System.ServiceModel.Channels.WebContentTypeMapper>, que permite al usuario controlar la asignación entre el tipo de contenido y el formato del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="54b23-106">This sample introduces the <xref:System.ServiceModel.Channels.WebContentTypeMapper> class, which allows the user to control the mapping between content type and body format.</span></span>  
  
 <span data-ttu-id="54b23-107">WCF proporciona un conjunto de asignaciones predeterminadas para los tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="54b23-107">WCF provides a set of default mappings for content types.</span></span> <span data-ttu-id="54b23-108">Por ejemplo, `application/json` se asigna a JSON y `text/xml` se asigna a XML.</span><span class="sxs-lookup"><span data-stu-id="54b23-108">For example, `application/json` maps to JSON and `text/xml` maps to XML.</span></span> <span data-ttu-id="54b23-109">Cualquier tipo de contenido que no está asignado a JSON o a XML, está asignado al formato binario sin formato.</span><span class="sxs-lookup"><span data-stu-id="54b23-109">Any content type that is not mapped to JSON or XML is mapped to raw binary format.</span></span>  
  
 <span data-ttu-id="54b23-110">En algunos escenarios (por ejemplo, estilo de inserción API), el programador del servicio no controla el tipo de contenido devuelto por el cliente.</span><span class="sxs-lookup"><span data-stu-id="54b23-110">In some scenarios (for example, push-style APIs), the service developer does not control the content type returned by the client.</span></span> <span data-ttu-id="54b23-111">Por ejemplo, los clientes podrían devolver JSON como `text/javascript` en lugar de `application/json`.</span><span class="sxs-lookup"><span data-stu-id="54b23-111">For example, clients might return JSON as `text/javascript` instead of `application/json`.</span></span> <span data-ttu-id="54b23-112">En este caso, el programador del servicio debe proporcionar un tipo que deriva de <xref:System.ServiceModel.Channels.WebContentTypeMapper> para administrar correctamente el tipo de contenido determinado, como se muestra en el código de muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="54b23-112">In this case, the service developer must provide a type that derives from <xref:System.ServiceModel.Channels.WebContentTypeMapper> to handle the given content type correctly, as shown in the following sample code.</span></span>  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="54b23-113">El tipo debe reemplazar el método <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="54b23-113">The type must override the <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> method.</span></span> <span data-ttu-id="54b23-114">El método debe evaluar el argumento `contentType` y devolver uno de los valores siguientes: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>o <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span><span class="sxs-lookup"><span data-stu-id="54b23-114">The method must evaluate the `contentType` argument and return one of the following values: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span></span> <span data-ttu-id="54b23-115">El devolver el <xref:System.ServiceModel.Channels.WebContentFormat.Default> difiere las asignaciones de codificador del mensaje de web predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="54b23-115">Returning <xref:System.ServiceModel.Channels.WebContentFormat.Default> defers to the default Web message encoder mappings.</span></span> <span data-ttu-id="54b23-116">En el código de ejemplo anterior, el tipo de contenido `text/javascript` está asignado a JSON y todas las demás asignaciones siguen estando sin modificar.</span><span class="sxs-lookup"><span data-stu-id="54b23-116">In the previous sample code, the `text/javascript` content type is mapped to JSON, and all other mappings remain unchanged.</span></span>  
  
 <span data-ttu-id="54b23-117">Para utilizar la clase `JsonContentTypeMapper`, utilice lo siguiente en el archivo Web.config:</span><span class="sxs-lookup"><span data-stu-id="54b23-117">To use the `JsonContentTypeMapper` class, use the following in your Web.config:</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="54b23-118">Para comprobar el requisito para utilizar JsonContentTypeMapper, quite el atributo contentTypeMapper del archivo de configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="54b23-118">To verify the requirement for using the JsonContentTypeMapper, remove the contentTypeMapper attribute from the above configuration file.</span></span> <span data-ttu-id="54b23-119">La página del cliente no se carga al intentar utilizar `text/javascript` para enviar el contenido JSON.</span><span class="sxs-lookup"><span data-stu-id="54b23-119">The client page fails to load when attempting to use `text/javascript` to send JSON content.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="54b23-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="54b23-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="54b23-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54b23-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="54b23-122">Compile la solución WebContentTypeMapperSample. sln tal y como se describe en [Building the Windows Communication Foundation samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54b23-122">Build the solution WebContentTypeMapperSample.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="54b23-123">Vaya a `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (no abra JCTMClientPage.htm en el explorador desde el directorio del proyecto).</span><span class="sxs-lookup"><span data-stu-id="54b23-123">Navigate to `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (do not open JCTMClientPage.htm in the browser from within the project directory).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54b23-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="54b23-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="54b23-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="54b23-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="54b23-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="54b23-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="54b23-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="54b23-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
