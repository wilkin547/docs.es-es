---
title: "C&#243;mo: Fragmentar datos serializados | Microsoft Docs"
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
  - "serialización binaria, fragmentar datos"
  - "serialización binaria, ejemplos"
  - "fragmentar datos serializados"
  - "fragmentación de datos"
  - "fragmentación de conjuntos de datos grandes"
  - "serialización, fragmentar datos"
  - "serialización, ejemplos"
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Fragmentar datos serializados
Dos problemas que se producen al enviar los conjuntos de datos grandes en mensajes del Servicio Web son:  
  
1.  Un espacio de trabajo grande \(memoria\) debido al almacenamiento en búfer por el motor de la serialización.  
  
2.  Consumo de ancho de banda inmoderado debido a 33 por ciento inflación después de la codificación de Base64.  
  
 Para resolver estos problemas, implemente la interfaz <xref:System.Xml.Serialization.IXmlSerializable> para controlar la serialización y deserialización.Específicamente, implemente <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> y los métodos <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> al fragmento los datos.  
  
### Para implementar la fragmentación del lado del servidor  
  
1.  En el equipo del servidor, el método web se debe apagar del almacenado en búfer de ASP.NET y devolver un tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>.  
  
2.  El tipo que implementa  <xref:System.Xml.Serialization.IXmlSerializable> fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
### Para implementar el procesamiento del lado cliente  
  
1.  Modifique el método Web en el proxy de cliente para devolver el tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>.Puede utilizar un <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> para realizar esta acción automáticamente, pero no se muestra aquí.  
  
2.  Implemente el método <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> para leer el flujo de datos fragmentado y escribir los bytes en el disco.Esta implementación también genera eventos de progreso que pueden ser utilizados por un control gráfico, como una barra de progreso.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra el método Web en el cliente que desactiva el almacenado en búfer de ASP.NET.También muestra la implementación del lado cliente de la interfaz <xref:System.Xml.Serialization.IXmlSerializable> que fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
 [!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
 [!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## Compilar el código  
  
-   El código utiliza los siguientes espacios de nombres: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, y <xref:System.Xml.Schema>.  
  
## Vea también  
 [Serialización personalizada](../../../docs/framework/serialization/custom-serialization.md)