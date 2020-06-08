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
ms.openlocfilehash: 1d38c4e334439ef41b4d4429e52cff04c6463573
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84291570"
---
# <a name="how-to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Procedimiento para serializar un objeto como secuencia XML con codificación SOAP
  
 Dado que un mensaje SOAP se genera mediante XML, se puede usar la clase <xref:System.Xml.Serialization.XmlSerializer> para serializar las clases y generar mensajes SOAP codificados. El XML resultante se ajusta a la [sección 5 del documento de World Wide Web Consortium, "Protocolo simple de acceso a objetos (SOAP) 1.1"](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/#_Toc478383512). Si está creando un servicio Web XML que se comunica a través de mensajes SOAP, puede personalizar la secuencia XML aplicando un conjunto de atributos SOAP especiales a las clases y miembros de clases. Para obtener más información, vea [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md).  
  
### <a name="to-serialize-an-object-as-a-soap-encoded-xml-stream"></a>Para serializar un objeto como secuencia XML con codificación SOAP  
  
1. Cree la clase mediante la [herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
2. Aplique uno o más de los atributos especiales situados en `System.Xml.Serialization`. Vea la lista en "Atributos que controlan la serialización SOAP codificada".  
  
3. Cree `XmlTypeMapping` creando un nuevo `SoapReflectionImporter`e invocando el método `ImportTypeMapping` con el tipo de la clase serializada.  
  
     En el ejemplo de código siguiente se llama al método `ImportTypeMapping` de la clase `SoapReflectionImporter` para crear `XmlTypeMapping`.  
  
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
  
4. Cree una instancia de la clase `XmlSerializer` pasando `XmlTypeMapping` al constructor <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5. Llame al método `Serialize` o `Deserialize`.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="see-also"></a>Vea también

- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md)
- [Serialización XML con servicios web XML](xml-serialization-with-xml-web-services.md)
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserializar un objeto](how-to-deserialize-an-object.md)
- [Cómo: Invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md)
