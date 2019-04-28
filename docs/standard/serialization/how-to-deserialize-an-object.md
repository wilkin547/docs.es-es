---
title: Procedimiento para deserializar un objeto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: 53b4a3e3848c1aa92bfa9fbd80bb031125257fc2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922725"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="22d77-102">Procedimiento para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="22d77-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="22d77-103">Al deserializar un objeto, el formato de transporte determina si creará una secuencia u objeto de archivo.</span><span class="sxs-lookup"><span data-stu-id="22d77-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="22d77-104">Una vez determinado el formato de transporte, puede llamar <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o los métodos <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, como se requiera.</span><span class="sxs-lookup"><span data-stu-id="22d77-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="22d77-105">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="22d77-105">To deserialize an object</span></span>  
  
1. <span data-ttu-id="22d77-106">Construya un<xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo del objeto para deserializar.</span><span class="sxs-lookup"><span data-stu-id="22d77-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2. <span data-ttu-id="22d77-107">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> para generar una réplica del objeto.</span><span class="sxs-lookup"><span data-stu-id="22d77-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="22d77-108">Al deserializar, debe convertir el objeto devuelto al tipo del original, como se muestra en el ejemplo siguiente, que deserializa el objeto en un archivo (aunque también se pudo deserializar en una secuencia).</span><span class="sxs-lookup"><span data-stu-id="22d77-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="22d77-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="22d77-109">See also</span></span>

- [<span data-ttu-id="22d77-110">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="22d77-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="22d77-111">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="22d77-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
