---
title: 'Cómo: Fragmentar datos serializados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- chunking serialized data
- data chunking
- binary serialization, chunking data
- large data set chunking
- serialization, chunking data
- serialization, examples
- binary serialization, examples
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
ms.openlocfilehash: 6a39997d8854d525146c044ed4bbf939de615d3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602428"
---
# <a name="how-to-chunk-serialized-data"></a>Cómo: Fragmentar datos serializados

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Dos problemas que se producen al enviar los conjuntos de datos grandes en mensajes del Servicio Web son:  
  
1. Un espacio de trabajo grande (memoria) debido al almacenamiento en búfer por el motor de la serialización.  
  
2. Consumo de ancho de banda inmoderado debido a 33 por ciento inflación después de la codificación de Base64.  
  
 Para resolver estos problemas, implemente la interfaz <xref:System.Xml.Serialization.IXmlSerializable> para controlar la serialización y deserialización. Específicamente, implemente <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> y los métodos <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> al fragmento los datos.  
  
### <a name="to-implement-server-side-chunking"></a>Para implementar la fragmentación del lado del servidor  
  
1. En el equipo del servidor, el método web se debe apagar del almacenado en búfer de ASP.NET y devolver un tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>.  
  
2. El tipo que implementa  <xref:System.Xml.Serialization.IXmlSerializable> fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
### <a name="to-implement-client-side-processing"></a>Para implementar el procesamiento del lado cliente  
  
1. Modifique el método Web en el proxy de cliente para devolver el tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>. Puede usar una <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> para realizar esta acción automáticamente, pero no se muestra aquí.  
  
2. Implemente el método <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> para leer el flujo de datos fragmentado y escribir los bytes en el disco. Esta implementación también genera eventos de progreso que pueden ser utilizados por un control gráfico, como una barra de progreso.  
  
## <a name="example"></a>Ejemplo  
El ejemplo de código siguiente muestra el método Web en el cliente que desactiva el almacenado en búfer de ASP.NET. También muestra la implementación del lado cliente de la interfaz <xref:System.Xml.Serialization.IXmlSerializable> que fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilación del código  
  
- El código utiliza los siguientes espacios de nombres: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, y <xref:System.Xml.Schema>.  
  
## <a name="see-also"></a>Vea también

- [Serialización personalizada](custom-serialization.md)
