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
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1ce7baf12c1826ddd14edad5e7dec328278c40e3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="49c4c-102">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="49c4c-102">How to: Serialize an Object</span></span>
<span data-ttu-id="49c4c-103">Para serializar un objeto, primero cree el objeto que será serializado y establezca</span><span class="sxs-lookup"><span data-stu-id="49c4c-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="49c4c-104">Debe determinar el formato de transporte en el que la secuencia XML estará almacenada, o como una secuencia o como un archivo, para ello.</span><span class="sxs-lookup"><span data-stu-id="49c4c-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="49c4c-105">Por ejemplo, si la secuencia XML debe estar guardada en un formulario permanente, cree un objeto <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="49c4c-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49c4c-106">Para obtener más ejemplos de serialización XML, vea [Ejemplos de serialización XML](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="49c4c-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="49c4c-107">Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="49c4c-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="49c4c-108">Cree el objeto y establezca sus campos públicos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="49c4c-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="49c4c-109">Construya un <xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="49c4c-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="49c4c-110">Para obtener más información, vea los constructores de clase <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="49c4c-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="49c4c-111">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> para generar o una secuencia XML o una representación del archivo de las propiedades públicas del objeto y campos.</span><span class="sxs-lookup"><span data-stu-id="49c4c-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="49c4c-112">En el ejemplo siguiente se crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="49c4c-112">The following example creates a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49c4c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="49c4c-113">See Also</span></span>  
 [<span data-ttu-id="49c4c-114">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="49c4c-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="49c4c-115">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="49c4c-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
