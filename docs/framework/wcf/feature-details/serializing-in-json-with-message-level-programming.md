---
title: Serializar en Json con programación en el nivel de mensajes
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: a2568c30d34e39aaf1708a9fb3e186f86b17f5b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498152"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serializar en Json con programación en el nivel de mensajes
WCF admite la serialización de datos en formato JSON. Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programación de mensajes con tipos  
 Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio. Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`. Para usar JSON para las solicitudes y las respuestas, establezca ambos en `WebMessageFormat.Json`.  Para poder usar JSON debe usar <xref:System.ServiceModel.WebHttpBinding>, que configura automáticamente <xref:System.ServiceModel.Description.WebHttpBehavior>. Para obtener más información acerca de la serialización de WCF, vea: [serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [serialización en Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx). Para obtener más información sobre JSON y WCF vea [Introducción a los servicios RESTful con WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [habilitados para JSON crear servicios de WCF en .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), y [información general sobre REST en WCF](http://msdn.microsoft.com/netframework/dd547388).  
  
> [!IMPORTANT]
>  El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP. Servicios que se comunican con el <xref:System.ServiceModel.WebHttpBinding> no admiten exponer metadatos de servicio, por lo que no podrán usar la funcionalidad de agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos svcutil para generar un proxy del lado cliente. Para obtener más información cómo se puede llamar mediante programación a servicios que utilizan <xref:System.ServiceModel.WebHttpBinding>, consulte [cómo consumir los servicios REST con WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## <a name="untyped-message-programming"></a>Programación de mensajes sin tipos  
 Al trabajar directamente con objetos de mensaje sin tipo, debe establecer explícitamente las propiedades del mensaje sin tipo para serializarlo como JSON. El siguiente fragmento de código muestra cómo hacerlo:  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a>Vea también  
 [Integración de AJAX y compatibilidad de JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [Serialización de JSON](../../../../docs/framework/wcf/samples/json-serialization.md)
