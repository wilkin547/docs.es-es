---
title: "Serializar en Json con programación en el nivel de mensajes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfa8952c54f29d88cb4975c1924b9c3e94c1c226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="5beee-102">Serializar en Json con programación en el nivel de mensajes</span><span class="sxs-lookup"><span data-stu-id="5beee-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="5beee-103">WCF admite la serialización de datos en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="5beee-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="5beee-104">Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5beee-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="5beee-105">Programación de mensajes con tipos</span><span class="sxs-lookup"><span data-stu-id="5beee-105">Typed Message Programming</span></span>  
 <span data-ttu-id="5beee-106">Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="5beee-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="5beee-107">Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="5beee-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="5beee-108">Para usar JSON para las solicitudes y las respuestas, establezca ambos en `WebMessageFormat.Json`.</span><span class="sxs-lookup"><span data-stu-id="5beee-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="5beee-109">Para poder usar JSON debe usar <xref:System.ServiceModel.WebHttpBinding>, que configura automáticamente <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5beee-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="5beee-110">Para obtener más información acerca de la serialización de WCF, vea: [serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [serialización en Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span><span class="sxs-lookup"><span data-stu-id="5beee-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="5beee-111">Para obtener más información sobre JSON y WCF vea [Introducción a los servicios RESTful con WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [habilitados para JSON crear servicios de WCF en .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), y [información general sobre REST en WCF](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="5beee-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5beee-112">El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP.</span><span class="sxs-lookup"><span data-stu-id="5beee-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="5beee-113">Servicios que se comunican con el <xref:System.ServiceModel.WebHttpBinding> no admiten exponer metadatos de servicio, por lo que no podrán usar la funcionalidad de agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos svcutil para generar un proxy del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="5beee-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="5beee-114">Para obtener más información cómo se puede llamar mediante programación a servicios que utilizan <xref:System.ServiceModel.WebHttpBinding>, consulte [cómo consumir los servicios REST con WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span><span class="sxs-lookup"><span data-stu-id="5beee-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="5beee-115">Programación de mensajes sin tipos</span><span class="sxs-lookup"><span data-stu-id="5beee-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="5beee-116">Al trabajar directamente con objetos de mensaje sin tipo, debe establecer explícitamente las propiedades del mensaje sin tipo para serializarlo como JSON.</span><span class="sxs-lookup"><span data-stu-id="5beee-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="5beee-117">El siguiente fragmento de código muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="5beee-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="5beee-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5beee-118">See Also</span></span>  
 [<span data-ttu-id="5beee-119">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="5beee-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="5beee-120">Serialización independiente de JSON</span><span class="sxs-lookup"><span data-stu-id="5beee-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="5beee-121">Serialización de JSON</span><span class="sxs-lookup"><span data-stu-id="5beee-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
