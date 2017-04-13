---
title: "C&#243;mo: Serializar un objeto como secuencia XML con codificaci&#243;n SOAP | Microsoft Docs"
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
  - "serialización, SOAP"
  - "SOAP, serialización XML"
  - "serialización XML, SOAP"
ms.assetid: af406e0a-fa3a-46dd-a7ba-c80731eba3a0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Serializar un objeto como secuencia XML con codificaci&#243;n SOAP
[Ejemplo de código](#cpconxmlserializationusingsoapprotocolanchor1)  
  
 Dado que un mensaje SOAP está generado utilizando XML, [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) se puede utilizar para serializar las clases y generar los mensajes SOAP codificados.El XML resultante se ajusta a la sección 5 del documento del Consorcio WWC \(www.w3.org\), "Protocolo de acceso simple a objetos \(SOAP\) 1.1".Si está creando un servicio Web XML que se comunica a través de mensajes SOAP, puede personalizar la secuencia XML aplicando un conjunto de atributos SOAP especiales a las clases y miembros de clases.Para obtener una lista de los atributos vea [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
### Para serializar un objeto como secuencia XML con codificación SOAP  
  
1.  Cree la clase utilizando [Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
2.  Aplique uno o más de los atributos especiales situados en **System.Xml.Serialization**.Vea la lista en "Atributos que controlan la serialización SOAP codificada".  
  
3.  Cree **XmlTypeMapping** creando un nuevo **SoapReflectionImporter**e invocando el método **ImportTypeMapping** con el tipo de la clase serializada.  
  
     En el ejemplo de código siguiente llama el método **ImportTypeMapping**de la clase **SoapReflectionImporter** para crear un**XmlTypeMapping**.  
  
    ```vb  
    ' Serializes a class named Group as a SOAP message.  
    Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
    ImportTypeMapping(GetType(Group))  
  
    ```  
  
    ```csharp  
    // Serializes a class named Group as a SOAP message.  
    XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().  
    ImportTypeMapping(typeof(Group));  
    ```  
  
4.  Cree una instancia de la clase **XmlSerializer** pasando **XmlTypeMapping** al constructor <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Xml.Serialization.XmlTypeMapping%29>.  
  
    ```vb  
    Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
    ```  
  
    ```csharp  
    XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
    ```  
  
5.  Llame al método **Serialize** o **Deserialize**.  
  
## Ejemplo  
  
```vb  
' Serializes a class named Group as a SOAP message.  
Dim myTypeMapping As XmlTypeMapping = (New SoapReflectionImporter(). _  
ImportTypeMapping(GetType(Group))  
Dim mySerializer As XmlSerializer = New XmlSerializer(myTypeMapping)  
  
```  
  
```csharp  
// Serializes a class named Group as a SOAP message.  
XmlTypeMapping myTypeMapping = (new SoapReflectionImporter().ImportTypeMapping(typeof(Group));  
XmlSerializer mySerializer = new XmlSerializer(myTypeMapping);  
```  
  
## Vea también  
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Atributos que controlan la serialización SOAP codificada](../../../docs/framework/serialization/attributes-that-control-encoded-soap-serialization.md)   
 [Serialización XML con servicios web XML](../../../docs/framework/serialization/xml-serialization-with-xml-web-services.md)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Cómo: Invalidar la serialización XML SOAP codificada](../../../docs/framework/serialization/how-to-override-encoded-soap-xml-serialization.md)