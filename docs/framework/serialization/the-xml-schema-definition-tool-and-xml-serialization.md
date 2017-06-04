---
title: "Herramienta de definici&#243;n de esquema XML y serializaci&#243;n XML | Microsoft Docs"
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
  - "Xsd.exe"
  - "serialización XML, herramienta de definición de esquema XML"
  - "herramienta de definición de esquema XML"
  - "serialización, herramienta de definición de esquema XML"
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Herramienta de definici&#243;n de esquema XML y serializaci&#243;n XML
La herramienta de definición de esquema XML \([Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)\) se instala junto con las herramientas de .NET Framework como parte del kit de desarrollo de software \(SDK\) de Windows®. La herramienta está diseñada para cumplir principalmente dos propósitos:  
  
-   Para crear archivos de clase C\# o para crearlos de clase Visual Basic y que así cumplan con un lenguaje de definición de esquema XML \(XSD\) concreto. La herramienta toma un esquema XML a modo de argumento, y genera un archivo que contiene varias clases que, al serializarlas con el elemento [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx), cumplen con el esquema. Para obtener más información sobre cómo usar la herramienta para generar clases que cumplan con un esquema en concreto, consulte [Cómo: Utilizar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
-   Generar un documento de esquema XML de un archivo .dll o .exe. Para ver el esquema de un conjunto de archivos que ha creado, o uno que se ha modificado con atributos, pase la DLL o el EXE como un argumento de la herramienta para generar el esquema XML. Para obtener más información sobre cómo utilizar la herramienta para generar un documento de esquema XML a partir de un conjunto de clases, consulte [Cómo: Utilizar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md).  
  
 Para obtener más información sobre esta herramienta y sobre otras, consulte [Tools](../../../docs/framework/tools/index.md). Para obtener más información sobre las opciones de las herramientas, consulte [Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## Vea también  
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [DataSet](frlrfSystemDataDataSetClassTopic)   
 [Herramienta de definición de esquema XML \(Xsd.exe\)](../../../docs/framework/serialization/xml-schema-definition-tool-xsd-exe.md)   
 [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)   
 [Cómo: Utilizar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/framework/serialization/xml-schema-def-tool-gen.md)   
 [Compatibilidad con enlaces del esquema XML en .NET Framework](http://msdn.microsoft.com/es-es/8f0619dd-f1fc-4895-ae21-6d45d0382cc1)