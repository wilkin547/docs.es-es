---
title: Procedimiento para serializar un objeto como secuencia XML con codificación SOAP
description: Aprenda a serializar un objeto como secuencia XML con codificación SOAP. La clase XmlSerializer se puede usar para serializar clases y generar mensajes SOAP codificados.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
ms.openlocfilehash: 09f1431d05248ef3ac3fdcf24bca35ff5cc2e22b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378393"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="98e00-104">Procedimiento para serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="98e00-104">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>
  
 <span data-ttu-id="98e00-105">Dado que un mensaje SOAP se genera mediante XML, se puede usar la clase <xref:System.Xml.Serialization.XmlSerializer> para serializar las clases y generar mensajes SOAP codificados.</span><span class="sxs-lookup"><span data-stu-id="98e00-105">Because a SOAP message is built using XML, the <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize classes and generate encoded SOAP messages.</span></span> <span data-ttu-id="98e00-106">El XML resultante se ajusta a la [sección 5 del documento de World Wide Web Consortium, "Protocolo simple de acceso a objetos (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span><span class="sxs-lookup"><span data-stu-id="98e00-106">The resulting XML conforms to [section 5 of the World Wide Web Consortium document "Simple Object Access Protocol (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512).</span></span> <span data-ttu-id="98e00-107">Si está creando un servicio Web XML que se comunica a través de mensajes SOAP, puede personalizar la secuencia XML aplicando un conjunto de atributos SOAP especiales a las clases y miembros de clases.</span><span class="sxs-lookup"><span data-stu-id="98e00-107">When you are creating an XML Web service that communicates through SOAP messages, you can customize the XML stream by applying a set of special SOAP attributes to classes and members of classes.</span></span> <span data-ttu-id="98e00-108">Para obtener más información, vea [Atributos que controlan la serialización SOAP codificada](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="98e00-108">For a list of attributes, see [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a><span data-ttu-id="98e00-109">Para serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="98e00-109">To serialize an object as a SOAP-encoded XML stream</span></span>  
  
1. <span data-ttu-id="98e00-110">Cree la clase mediante la [herramienta de definición de esquema XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="98e00-110">Create the class using the [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
2. <span data-ttu-id="98e00-111">Aplique uno o más de los atributos especiales situados en `System.Xml.Serialization`.</span><span class="sxs-lookup"><span data-stu-id="98e00-111">Apply one or more of the special attributes found in `System.Xml.Serialization`.</span></span> <span data-ttu-id="98e00-112">Vea la lista en "Atributos que controlan la serialización SOAP codificada".</span><span class="sxs-lookup"><span data-stu-id="98e00-112">See the list in "Attributes That Control Encoded SOAP Serialization."</span></span>  
  
3. <span data-ttu-id="98e00-113">Cree `XmlTypeMapping` creando un nuevo `SoapReflectionImporter`e invocando el método `ImportTypeMapping` con el tipo de la clase serializada.</span><span class="sxs-lookup"><span data-stu-id="98e00-113">Create an `XmlTypeMapping` by creating a new `SoapReflectionImporter`, and invoking the `ImportTypeMapping` method with the type of the serialized class.</span></span>  
  
     <span data-ttu-id="98e00-114">En el ejemplo de código siguiente se llama al método `ImportTypeMapping` de la clase `SoapReflectionImporter` para crear `XmlTypeMapping`.</span><span class="sxs-lookup"><span data-stu-id="98e00-114">The following code example calls the `ImportTypeMapping` method of the `SoapReflectionImporter` class to create an `XmlTypeMapping`.</span></span>  
  
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
  
4. <span data-ttu-id="98e00-115">Cree una instancia de la clase `XmlSerializer` pasando `XmlTypeMapping` al constructor <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.</span><span class="sxs-lookup"><span data-stu-id="98e00-115">Create an instance of the `XmlSerializer` class by passing the `XmlTypeMapping` to the <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29> constructor.</span></span>  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. <span data-ttu-id="98e00-116">Llame al método `Serialize` o `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="98e00-116">Call the `Serialize` or `Deserialize` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e00-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98e00-117">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98e00-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="98e00-118">See also</span></span>

- [<span data-ttu-id="98e00-119">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="98e00-119">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- [<span data-ttu-id="98e00-120">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="98e00-120">Attributes That Control Encoded SOAP Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)
- [<span data-ttu-id="98e00-121">Serialización XML con servicios web XML</span><span class="sxs-lookup"><span data-stu-id="98e00-121">XML Serialization with XML Web Services</span></span>](../../../docs/standard/serialization/xml-serialization-with-xml-web-services.md)
- [<span data-ttu-id="98e00-122">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="98e00-122">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="98e00-123">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="98e00-123">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="98e00-124">Cómo: Invalidar la serialización XML SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="98e00-124">How to: Override Encoded SOAP XML Serialization</span></span>](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)
