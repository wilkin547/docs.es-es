---
title: Herramienta de definición de esquema XML y serialización XML
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: b51b9a0112893d9a7838155f4af051e7079c8cdd
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588390"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Herramienta de definición de esquema XML y serialización XML

La herramienta Definición de esquemas XML ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md))&reg; se instala junto con las herramientas de .NET Framework como parte del Kit de desarrollo de software (SDK) de Windows. La herramienta está diseñada para cumplir principalmente dos propósitos:  
  
- Para crear archivos de clase C# o para crearlos de clase Visual Basic y que así cumplan con un lenguaje de definición de esquema XML (XSD) concreto. La herramienta toma un Esquema XML como un argumento y genera un archivo que contiene varias clases que cuando se serializa con <xref:System.Xml.Serialization.XmlSerializer>, cumpla al esquema. Para obtener más información sobre cómo usar la herramienta para generar clases que cumplan con un esquema en concreto, consulte [Cómo: Utilizar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
- Generar un documento de esquema XML de un archivo .dll o .exe. Para ver el esquema de un conjunto de archivos que ha creado, o uno que se ha modificado con atributos, pase la DLL o el EXE como un argumento de la herramienta para generar el esquema XML. Para obtener más información sobre cómo usar la herramienta para generar un documento de esquema XML a partir de un conjunto de clases, consulte [Cómo: Utilizar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
Para obtener más información sobre el uso de la herramienta, vea Herramienta de definición de [esquemas XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataSet>
- [Introducir la serialización XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procedimiento para serializar un objeto](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Procedimiento para deserializar un objeto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [Compatibilidad con enlaces del esquema XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
