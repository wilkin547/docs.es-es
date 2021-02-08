---
description: 'Más información sobre: serialización en JSON con programación de nivel de mensaje'
title: Serializar en Json con programación en el nivel de mensajes
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 715e44b0e2137197f5883e2327288555513f29cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793550"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="d6316-103">Serializar en Json con programación en el nivel de mensajes</span><span class="sxs-lookup"><span data-stu-id="d6316-103">Serializing in Json with Message Level Programming</span></span>

<span data-ttu-id="d6316-104">WCF admite la serialización de datos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="d6316-104">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="d6316-105">Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d6316-105">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="d6316-106">Programación de mensajes con tipos</span><span class="sxs-lookup"><span data-stu-id="d6316-106">Typed Message Programming</span></span>  

 <span data-ttu-id="d6316-107">Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="d6316-107">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="d6316-108">Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="d6316-108">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="d6316-109">Para usar JSON para las solicitudes y respuestas.</span><span class="sxs-lookup"><span data-stu-id="d6316-109">To use JSON for requests and responses.</span></span> <span data-ttu-id="d6316-110">establezca ambos en `WebMessageFormat.Json` .</span><span class="sxs-lookup"><span data-stu-id="d6316-110">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="d6316-111">Para usar JSON, debe usar el <xref:System.ServiceModel.WebHttpBinding> , que configura automáticamente el <xref:System.ServiceModel.Description.WebHttpBehavior> .</span><span class="sxs-lookup"><span data-stu-id="d6316-111">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="d6316-112">Para obtener más información sobre la serialización de WCF, vea [serialización y deserialización](serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="d6316-112">For more information about WCF serialization, see [Serialization and Deserialization](serialization-and-deserialization.md).</span></span> <span data-ttu-id="d6316-113">Para obtener más información sobre JSON y WCF, vea [estación de servicio: una introducción a los servicios RESTful con WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="d6316-113">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d6316-114">El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP.</span><span class="sxs-lookup"><span data-stu-id="d6316-114">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="d6316-115">Los servicios que se comunican con no <xref:System.ServiceModel.WebHttpBinding> admiten exponer metadatos de servicio, por lo que no podrá usar la funcionalidad de agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos SvcUtil para generar un proxy del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="d6316-115">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="d6316-116">Para obtener más información sobre cómo llamar a los servicios que usan mediante programación <xref:System.ServiceModel.WebHttpBinding> , vea [Cómo usar servicios REST con WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="d6316-116">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="d6316-117">Programación de mensajes sin tipos</span><span class="sxs-lookup"><span data-stu-id="d6316-117">Untyped Message Programming</span></span>  

 <span data-ttu-id="d6316-118">Al trabajar directamente con objetos de mensaje sin tipo, debe establecer explícitamente las propiedades del mensaje sin tipo para serializarlo como JSON.</span><span class="sxs-lookup"><span data-stu-id="d6316-118">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="d6316-119">El siguiente fragmento de código muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="d6316-119">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6316-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6316-120">See also</span></span>

- [<span data-ttu-id="d6316-121">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="d6316-121">AJAX Integration and JSON Support</span></span>](ajax-integration-and-json-support.md)
- [<span data-ttu-id="d6316-122">Serialización independiente de JSON</span><span class="sxs-lookup"><span data-stu-id="d6316-122">Stand-Alone JSON Serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="d6316-123">Serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="d6316-123">JSON Serialization</span></span>](../samples/json-serialization.md)
