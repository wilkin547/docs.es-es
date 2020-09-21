---
title: Herramienta de definición de esquema XML y serialización XML
description: La herramienta de definición de esquema XML genera archivos de clase de C# o Visual Basic para un esquema XSD y genera un esquema XML a partir de una biblioteca o un archivo ejecutable.
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: 6451f3b5f6e8ec2c1454e5cf7ffb95a96b620214
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554988"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Herramienta de definición de esquema XML y serialización XML

La herramienta de definición de esquema XML ([Herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) se instala junto con las herramientas de .NET Framework como parte del kit de desarrollo de software (SDK) de Windows&reg;. La herramienta está diseñada para cumplir principalmente dos propósitos:  
  
- Para crear archivos de clase C# o para crearlos de clase Visual Basic y que así cumplan con un lenguaje de definición de esquema XML (XSD) concreto. La herramienta toma un Esquema XML como un argumento y genera un archivo que contiene varias clases que cuando se serializa con <xref:System.Xml.Serialization.XmlSerializer>, cumpla al esquema. Para más información sobre cómo usar la herramienta para generar clases que cumplan con un esquema en concreto, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](xml-schema-def-tool-gen.md).  
  
- Generar un documento de esquema XML de un archivo .dll o .exe. Para ver el esquema de un conjunto de archivos que ha creado, o uno que se ha modificado con atributos, pase la DLL o el EXE como un argumento de la herramienta para generar el esquema XML. Para más información sobre cómo usar la herramienta para generar un documento de esquema XML a partir de un conjunto de clases, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](xml-schema-def-tool-gen.md).  
  
Para más información sobre cómo usar la herramienta, vea [Herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataSet>
- [Introducción a la serialización XML](introducing-xml-serialization.md)
- [Herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserializar un objeto](how-to-deserialize-an-object.md)
- [Cómo: Usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](xml-schema-def-tool-gen.md)
- [Compatibilidad con enlaces del esquema XML](/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
