---
title: Deserialización de un objeto con XmlSerializer
description: Aprenda a deserializar un objeto. El formato de transporte determina si se debe crear un objeto de secuencia o de archivo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e08ae0d77539219223650fd3bcbd1bcee4df2739
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379113"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="6e98a-104">Deserialización de un objeto con XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="6e98a-104">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="6e98a-105">Al deserializar un objeto, el formato de transporte determina si creará una secuencia u objeto de archivo.</span><span class="sxs-lookup"><span data-stu-id="6e98a-105">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="6e98a-106">Una vez determinado el formato de transporte, puede llamar <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o los métodos <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, como se requiera.</span><span class="sxs-lookup"><span data-stu-id="6e98a-106">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="6e98a-107">Para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="6e98a-107">To deserialize an object</span></span>

1. <span data-ttu-id="6e98a-108">Construya un<xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo del objeto para deserializar.</span><span class="sxs-lookup"><span data-stu-id="6e98a-108">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="6e98a-109">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> para generar una réplica del objeto.</span><span class="sxs-lookup"><span data-stu-id="6e98a-109">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="6e98a-110">Al deserializar, debe convertir el objeto devuelto al tipo del original, tal y como se muestra en el ejemplo siguiente, que deserializa el objeto en un archivo (aunque también se podía deserializar en una secuencia).</span><span class="sxs-lookup"><span data-stu-id="6e98a-110">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6e98a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e98a-111">See also</span></span>

- [<span data-ttu-id="6e98a-112">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="6e98a-112">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="6e98a-113">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="6e98a-113">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
