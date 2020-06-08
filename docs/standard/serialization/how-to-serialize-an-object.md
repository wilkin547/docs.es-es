---
title: Procedimiento para serializar un objeto
description: En este artículo se muestra cómo serializar un objeto. Seleccione un formato de transporte en el que se almacena la secuencia XML, ya sea como una secuencia o como un archivo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: e9c7ba250995db1c7a701de346b18661892e7e23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291557"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="65491-104">Procedimiento para serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="65491-104">How to: Serialize an Object</span></span>
<span data-ttu-id="65491-105">Para serializar un objeto, primero cree el objeto que será serializado y establezca</span><span class="sxs-lookup"><span data-stu-id="65491-105">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="65491-106">Debe determinar el formato de transporte en el que la secuencia XML estará almacenada, o como una secuencia o como un archivo, para ello.</span><span class="sxs-lookup"><span data-stu-id="65491-106">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="65491-107">Por ejemplo, si la secuencia XML debe estar guardada en un formulario permanente, cree un objeto <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="65491-107">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65491-108">Para obtener más ejemplos de serialización XML, vea [Ejemplos de serialización XML](examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="65491-108">For more examples of XML serialization, see [Examples of XML Serialization](examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="65491-109">Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="65491-109">To serialize an object</span></span>  
  
1. <span data-ttu-id="65491-110">Cree el objeto y establezca sus campos públicos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="65491-110">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="65491-111">Construya un <xref:System.Xml.Serialization.XmlSerializer> utilizando el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="65491-111">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="65491-112">Para obtener más información, vea los constructores de clase <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="65491-112">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="65491-113">Llame al método <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> para generar o una secuencia XML o una representación del archivo de las propiedades públicas del objeto y campos.</span><span class="sxs-lookup"><span data-stu-id="65491-113">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="65491-114">En el ejemplo siguiente se crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="65491-114">The following example creates a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65491-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="65491-115">See also</span></span>

- [<span data-ttu-id="65491-116">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="65491-116">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="65491-117">Cómo: Deserialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="65491-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
