---
title: "Cómo: Serializar un objeto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92f7d19d84f8146a5c7933119874f4223dc20b6b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-serialize-an-object"></a>Cómo: Serializar un objeto
Para serializar un objeto, primero cree el objeto que será serializado y establezca Debe determinar el formato de transporte en el que la secuencia XML estará almacenada, o como una secuencia o como un archivo, para ello. Por ejemplo, si la secuencia XML debe estar guardada en un formulario permanente, cree un objeto <xref:System.IO.FileStream>.  
  
> [!NOTE]
>  Para obtener más ejemplos de serialización XML, vea [Ejemplos de serialización XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Serializar un objeto  
  
1.  Cree el objeto y establezca sus campos públicos y propiedades.  
  
2.  Construya un <xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo de objeto. Para obtener más información, vea los constructores de clase <xref:System.Xml.Serialization.XmlSerializer> .  
  
3.  Llame al método <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> para generar o una secuencia XML o una representación del archivo de las propiedades públicas del objeto y campos. En el ejemplo siguiente se crea un archivo.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la serialización XML](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [Cómo: Deserializar un objeto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
