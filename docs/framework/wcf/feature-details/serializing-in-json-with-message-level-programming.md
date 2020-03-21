---
title: Serializar en Json con programación en el nivel de mensajes
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 36459dbc0ddee883678a98a27f9abb74fde78e86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184496"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serializar en Json con programación en el nivel de mensajes
WCF admite la serialización de datos en formato JSON. Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programación de mensajes con tipos  
 Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio. Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`. Para usar JSON para solicitudes y respuestas. establecer ambos en `WebMessageFormat.Json`.  Para utilizar JSON, debe utilizar <xref:System.ServiceModel.WebHttpBinding>el archivo , <xref:System.ServiceModel.Description.WebHttpBehavior>que configura automáticamente el archivo . Para obtener más información acerca de la serialización de WCF, vea [serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Para obtener más información acerca de JSON y WCF, vea [Service Station : una introducción a los servicios RESTful con WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP. Los servicios que <xref:System.ServiceModel.WebHttpBinding> se comunican con la no admiten la exposición de metadatos de servicio por lo que no podrá usar la funcionalidad Agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos svcutil para generar un proxy del lado cliente. Para obtener más información sobre cómo <xref:System.ServiceModel.WebHttpBinding>llamar mediante programación a los servicios que usan , vea [cómo consumir servicios REST con WCF](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).  
  
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
  
## <a name="see-also"></a>Consulte también

- [Integración de AJAX y compatibilidad de JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [Serialización JSON](../../../../docs/framework/wcf/samples/json-serialization.md)
