---
title: "Serializaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "serialización binaria"
  - "objetos, serializar"
  - "serialización"
  - "serializar objetos"
  - "serialización XML, definición"
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serializaci&#243;n
La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar.El complemento de serialización es deserialización, que convierte una secuencia en un objeto.Juntos, estos procesos permiten almacenar los datos y transferirlos con facilidad.  
  
 .NET Framework representa dos tecnologías serializando:  
  
-   La serialización binaria conserva fidelidad de tipo, que es útil para conservar el estado de un objeto entre las invocaciones diferentes de una aplicación.Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles.Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc.La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.  
  
-   La serialización XML serializa solo propiedades públicas y campos y no conserva la fidelidad de tipo.Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos.Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web.SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.  
  
## En esta sección  
 [Temas "Cómo…" sobre serialización](../../../docs/framework/serialization/serialization-how-to-topics.md)  
 Enumera vínculos a los temas "Cómo..." incluidos en esta sección.  
  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)  
 Describe el mecanismo de la serialización binaria que está incluido con Common Language Runtime.  
  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Describe el mecanismo de la serialización XML y SOAP que está incluido con Common Language Runtime.  
  
 [Herramientas de serialización](../../../docs/framework/serialization/serialization-tools.md)  
 Estas herramientas ayudan a desarrollar el código de serialización.  
  
 [Ejemplos de serialización](../../../docs/framework/serialization/serialization-samples.md)  
 En los ejemplos se muestra cómo hacer la serialización.  
  
## Referencia  
 <xref:System.Runtime.Serialization>  
 Contiene clases que se pueden utilizar para serializar y deserializar objetos.  
  
 <xref:System.Xml.Serialization>  
 Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.  
  
## Secciones relacionadas  
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)  
 Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.  
  
 [Advanced Development Technologies](http://msdn.microsoft.com/es-es/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 Proporciona vínculos para más información sobre tareas y técnicas de desarrollo sofisticadas de .NET Framework.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/es-es/1e64af78-d705-4384-b08d-591a45f4379c)  
 Proporciona los temas que describen y explican cómo programar los servicios Web XML creados utilizando ASP.NET.