---
title: "C&#243;mo: Serializar un objeto | Microsoft Docs"
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
  - "objetos, pasos de serialización"
  - "serializar objetos"
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Serializar un objeto
Para serializar un objeto, primero cree el objeto que será serializado y establezca sus propiedades y campos públicos.Debe determinar el formato de transporte en el que la secuencia XML estará almacenada, o como una secuencia o como un archivo, para ello.Por ejemplo, si la secuencia XML debe estar guardada en un formulario permanente, cree un objeto [FileStream](frlrfSystemIOFileStreamClassTopic).  
  
> [!NOTE]
>  Para ver más ejemplos de serialización XML vea [Ejemplos de serialización XML](../../../docs/framework/serialization/examples-of-xml-serialization.md).  
  
### Serializar un objeto  
  
1.  Cree el objeto y establezca sus campos públicos y propiedades.  
  
2.  Construya un <xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo de objeto.Para obtener más información, vea los constructores de clase <xref:System.Xml.Serialization.XmlSerializer> .  
  
3.  Llame al método <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> para generar o una secuencia XML o una representación del archivo de las propiedades públicas del objeto y campos.En el ejemplo siguiente se crea un archivo.  
  
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
  
## Vea también  
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)