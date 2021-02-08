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
# <a name="serializing-in-json-with-message-level-programming"></a>Serializar en Json con programación en el nivel de mensajes

WCF admite la serialización de datos en formato JSON. Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programación de mensajes con tipos  

 Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio. Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`. Para usar JSON para las solicitudes y respuestas. establezca ambos en `WebMessageFormat.Json` .  Para usar JSON, debe usar el <xref:System.ServiceModel.WebHttpBinding> , que configura automáticamente el <xref:System.ServiceModel.Description.WebHttpBehavior> . Para obtener más información sobre la serialización de WCF, vea [serialización y deserialización](serialization-and-deserialization.md). Para obtener más información sobre JSON y WCF, vea [estación de servicio: una introducción a los servicios RESTful con WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP. Los servicios que se comunican con no <xref:System.ServiceModel.WebHttpBinding> admiten exponer metadatos de servicio, por lo que no podrá usar la funcionalidad de agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos SvcUtil para generar un proxy del lado cliente. Para obtener más información sobre cómo llamar a los servicios que usan mediante programación <xref:System.ServiceModel.WebHttpBinding> , vea [Cómo usar servicios REST con WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).  
  
## <a name="untyped-message-programming"></a>Programación de mensajes sin tipos  

 Al trabajar directamente con objetos de mensaje sin tipo, debe establecer explícitamente las propiedades del mensaje sin tipo para serializarlo como JSON. El siguiente fragmento de código muestra cómo hacerlo:  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a>Vea también

- [Integración de AJAX y compatibilidad de JSON](ajax-integration-and-json-support.md)
- [Serialización independiente de JSON](stand-alone-json-serialization.md)
- [Serialización de JSON](../samples/json-serialization.md)
