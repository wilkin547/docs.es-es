---
title: "Serializar en Json con programaci&#243;n en el nivel de mensajes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Serializar en Json con programaci&#243;n en el nivel de mensajes
WCF admite la serialización de datos en formato JSON.Este tema describe cómo indicar a WCF que serialice sus tipos mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## Programación de mensajes con tipos  
 Se usa <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> cuando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> se aplica a una operación de servicio.Ambos atributos permiten especificar `RequestFormat` y `ResponseFormat`.Para usar JSON para las solicitudes y las respuestas, establezca ambos en `WebMessageFormat.Json`.Para poder usar JSON debe usar <xref:System.ServiceModel.WebHttpBinding>, que configura automáticamente <xref:System.ServiceModel.Description.WebHttpBehavior>.Para obtener más información sobre la serialización de WCF, vea: [Serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialización en Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).Para obtener más información sobre JSON y WCF, vea [Introducción a servicios RESTfull con WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Crear servicios de WCF habilitados para JSON en .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx) e [Información general del modelo de programación web HTTP de WCF](http://msdn.microsoft.com/netframework/dd547388).  
  
> [!IMPORTANT]
>  El uso de JSON requiere el uso de <xref:System.ServiceModel.WebHttpBinding> y <xref:System.ServiceModel.Description.WebHttpBehavior>, que no admiten la comunicación SOAP.Los servicios que se comunican con <xref:System.ServiceModel.WebHttpBinding> no admiten exponer metadatos de servicio por lo que no podrá usar la funcionalidad Agregar referencia de servicio de Visual Studio o la herramienta de línea de comandos svcutil para generar un proxy del lado cliente.Para obtener más información sobre cómo se puede llamar mediante programación a servicios que usan <xref:System.ServiceModel.WebHttpBinding>, vea [Cómo usar servicios REST con WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## Programación de mensajes sin tipos  
 Al trabajar directamente con objetos de mensaje sin tipo, debe establecer explícitamente las propiedades del mensaje sin tipo para serializarlo como JSON.El siguiente fragmento de código muestra cómo hacerlo:  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
  
```  
  
## Vea también  
 [Integración de AJAX y compatibilidad de JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [Serialización independiente de JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [Serialización JSON](../../../../docs/framework/wcf/samples/json-serialization.md)