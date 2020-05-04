---
title: Deserialización de un objeto con XmlSerializer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: c24ba466a208fe5abdbf565169c41c4ee3f47482
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559903"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="dc58c-102">Deserialización de un objeto con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="dc58c-102">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="dc58c-103">Al deserializar un objeto, el formato de transporte determina si creará una secuencia u objeto de archivo.</span><span class="sxs-lookup"><span data-stu-id="dc58c-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="dc58c-104">Una vez determinado el formato de transporte, puede llamar <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o los métodos <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, como se requiera.</span><span class="sxs-lookup"><span data-stu-id="dc58c-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="dc58c-105">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="dc58c-105">To deserialize an object</span></span>

1. <span data-ttu-id="dc58c-106">Construya un<xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo del objeto para deserializar.</span><span class="sxs-lookup"><span data-stu-id="dc58c-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="dc58c-107">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> para generar una réplica del objeto.</span><span class="sxs-lookup"><span data-stu-id="dc58c-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="dc58c-108">Al deserializar, debe convertir el objeto devuelto al tipo del original, tal y como se muestra en el ejemplo siguiente, que deserializa el objeto en un archivo (aunque también se podía deserializar en una secuencia).</span><span class="sxs-lookup"><span data-stu-id="dc58c-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

    ```vb
    ' Construct an instance of the XmlSerializer with the type
    ' of object that is being deserialized.
    Dim mySerializer As New XmlSerializer(GetType(MySerializableClass))
    ' To read the file, create a FileStream.
    Dim myFileStream As New FileStream("myFileName.xml", FileMode.Open)
    ' Call the Deserialize method and cast to the object type.
    Dim myObject = CType( _
    mySerializer.Deserialize(myFileStream), MySerializableClass)
    ```

    ```csharp
    // Construct an instance of the XmlSerializer with the type
    // of object that is being deserialized.
    var mySerializer = new XmlSerializer(typeof(MySerializableClass));
    // To read the file, create a FileStream.
    var myFileStream = new FileStream("myFileName.xml", FileMode.Open);
    // Call the Deserialize method and cast to the object type.
    var myObject = (MySerializableClass) mySerializer.Deserialize(myFileStream)
    ```

## <a name="see-also"></a><span data-ttu-id="dc58c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc58c-109">See also</span></span>

- [<span data-ttu-id="dc58c-110">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="dc58c-110">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="dc58c-111">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="dc58c-111">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
