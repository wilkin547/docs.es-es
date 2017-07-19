---
title: "Formateador de suministro (JSON) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Formateador de suministro (JSON)
Este ejemplo muestra cómo serializar una instancia de una clase <xref:System.ServiceModel.Syndication.SyndicationFeed> en el formato de la Notación de objeto JavaScript \(JSON\) utilizando un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizado y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## Arquitectura del ejemplo  
 El ejemplo implementa una clase denominada `JsonFeedFormatter` que se hereda desde <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.  La clase `JsonFeedFormatter` confía en que <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> lea y escriba los datos en formato de JSON.  Internamente, el formateador utiliza un conjunto personalizado de tipos de contrato de datos denominado `JsonSyndicationFeed` y `JsonSyndicationItem` para controlar el formato de los datos de JSON generado por el serializador.  Estos detalles de implementación se ocultan del usuario final, permitiendo realizar las llamadas contra los <xref:System.ServiceModel.Syndication.SyndicationFeed> estándar y las clases <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
## Escribir las fuentes de JSON  
 Escribir una fuente de JSON se puede lograr utilizando `JsonFeedFormatter` \(se implementa en este ejemplo\) con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> como se muestra en el código muestra siguiente.  
  
```  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
  
```  
  
## Leer una fuente de JSON  
 Obtener una <xref:System.ServiceModel.Syndication.SyndicationFeed> de una secuencia de datos dados formateados por JSON se puede lograr con `JsonFeedFormatter` como presentación en el código siguiente.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar el procedimiento de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
  
## Vea también