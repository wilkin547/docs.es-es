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
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588390"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="eaa77-102">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="eaa77-102">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="eaa77-103">La herramienta de definición de esquema XML ([Herramienta de definición de esquema XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) se instala junto con las herramientas de .NET Framework como parte del kit de desarrollo de software (SDK) de Windows&reg;.</span><span class="sxs-lookup"><span data-stu-id="eaa77-103">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="eaa77-104">La herramienta está diseñada para cumplir principalmente dos propósitos:</span><span class="sxs-lookup"><span data-stu-id="eaa77-104">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="eaa77-105">Para crear archivos de clase C# o para crearlos de clase Visual Basic y que así cumplan con un lenguaje de definición de esquema XML (XSD) concreto.</span><span class="sxs-lookup"><span data-stu-id="eaa77-105">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="eaa77-106">La herramienta toma un Esquema XML como un argumento y genera un archivo que contiene varias clases que cuando se serializa con <xref:System.Xml.Serialization.XmlSerializer>, cumpla al esquema.</span><span class="sxs-lookup"><span data-stu-id="eaa77-106">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="eaa77-107">Para más información sobre cómo usar la herramienta para generar clases que cumplan con un esquema en concreto, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="eaa77-107">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="eaa77-108">Generar un documento de esquema XML de un archivo .dll o .exe.</span><span class="sxs-lookup"><span data-stu-id="eaa77-108">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="eaa77-109">Para ver el esquema de un conjunto de archivos que ha creado, o uno que se ha modificado con atributos, pase la DLL o el EXE como un argumento de la herramienta para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="eaa77-109">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="eaa77-110">Para más información sobre cómo usar la herramienta para generar un documento de esquema XML a partir de un conjunto de clases, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="eaa77-110">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="eaa77-111">Para más información sobre cómo usar la herramienta, vea [Herramienta de definición de esquema XML (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="eaa77-111">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa77-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaa77-112">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="eaa77-113">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="eaa77-113">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="eaa77-114">Herramienta de definición de esquema XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="eaa77-114">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="eaa77-115">Cómo: serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="eaa77-115">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="eaa77-116">Cómo: deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="eaa77-116">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [<span data-ttu-id="eaa77-117">Cómo: Usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="eaa77-117">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- <span data-ttu-id="eaa77-118">[Compatibilidad con enlaces del esquema XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eaa77-118">[XML Schema Binding Support](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
