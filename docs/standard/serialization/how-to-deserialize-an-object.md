---
title: 'Cómo: Deserializar un objeto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: 957c332b3456e2b27aca36ef2bcabbc36b4e94e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581487"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="c0cf6-102">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="c0cf6-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="c0cf6-103">Al deserializar un objeto, el formato de transporte determina si creará una secuencia u objeto de archivo.</span><span class="sxs-lookup"><span data-stu-id="c0cf6-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="c0cf6-104">Una vez determinado el formato de transporte, puede llamar <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o los métodos <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, como se requiera.</span><span class="sxs-lookup"><span data-stu-id="c0cf6-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="c0cf6-105">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="c0cf6-105">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="c0cf6-106">Construya un<xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo del objeto para deserializar.</span><span class="sxs-lookup"><span data-stu-id="c0cf6-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2.  <span data-ttu-id="c0cf6-107">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> para generar una réplica del objeto.</span><span class="sxs-lookup"><span data-stu-id="c0cf6-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="c0cf6-108">Al deserializar, debe convertir el objeto devuelto al tipo del original, como se muestra en el ejemplo siguiente, que deserializa el objeto en un archivo (aunque también se pudo deserializar en una secuencia).</span><span class="sxs-lookup"><span data-stu-id="c0cf6-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0cf6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0cf6-109">See Also</span></span>  
 [<span data-ttu-id="c0cf6-110">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="c0cf6-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="c0cf6-111">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="c0cf6-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
