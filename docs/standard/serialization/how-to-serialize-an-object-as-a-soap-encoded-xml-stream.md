---
title: Procedimiento para serializar un objeto como secuencia XML con codificación SOAP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: bfbdda0861a6f2867a2e7003dd7054129fd343b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018026"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="46f94-102">Procedimiento para serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="46f94-102">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="46f94-103">Dado que un mensaje SOAP se genera mediante XML, se puede usar la clase <xref:System.Xml.Serialization.XmlSerializer> para serializar las clases y generar mensajes SOAP codificados.</span><span class="sxs-lookup"><span data-stu-id="46f94-103">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="46f94-104">El XML resultante se ajusta a la [sección 5 del documento de World Wide Web Consortium, "Protocolo simple de acceso a objetos (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="46f94-104">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="46f94-105">Si está creando un servicio Web XML que se comunica a través de mensajes SOAP, puede personalizar la secuencia XML aplicando un conjunto de atributos SOAP especiales a las clases y miembros de clases.</span><span class="sxs-lookup"><span data-stu-id="46f94-105">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="46f94-106">Para obtener más información, vea [Atributos que controlan la serialización SOAP codificada](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="46f94-106">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="46f94-107">Para serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="46f94-107">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="46f94-108">Cree la clase mediante la [herramienta de definición de esquema XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="46f94-108">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="46f94-109">Aplique uno o más de los atributos especiales situados en `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="46f94-109">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="46f94-110">Vea la lista en "Atributos que controlan la serialización SOAP codificada".</span><span class="sxs-lookup"><span data-stu-id="46f94-110">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="46f94-111">Cree `XmlTypeMapping` creando un nuevo `SoapReflectionImporter`e invocando el método `ImportTypeMapping` con el tipo de la clase serializada.</span><span class="sxs-lookup"><span data-stu-id="46f94-111">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="46f94-112">En el ejemplo de código siguiente se llama al método `ImportTypeMapping` de la clase `SoapReflectionImporter` para crear `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="46f94-112">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping =
        New SoapReflectionImporter().ImportTypeMapping(GetType(Group))  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping =
        new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
    ```  
  
4. <span data-ttu-id="46f94-113">Cree una instancia de la clase `XmlSerializer` pasando `XmlTypeMapping` al constructor <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="46f94-113">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="46f94-114">Llame al método `Serialize` o `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="46f94-114">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46f94-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46f94-115">Example</span></span>  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping =
    New SoapReflectionImporter().ImportTypeMapping(GetType(Group))
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping =
    new SoapReflectionImporter().ImportTypeMapping(typeof(Group));
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## <a name="see-also"></a><span data-ttu-id="46f94-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="46f94-116">See also</span></span>

- [<span data-ttu-id="46f94-117">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="46f94-117">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- [<span data-ttu-id="46f94-118">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="46f94-118">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="46f94-119">Serialización XML con servicios web XML</span><span class="sxs-lookup"><span data-stu-id="46f94-119">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="46f94-120">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="46f94-120">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="46f94-121">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="46f94-121">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="46f94-122">Cómo: Invalidar la serialización XML SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="46f94-122">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
