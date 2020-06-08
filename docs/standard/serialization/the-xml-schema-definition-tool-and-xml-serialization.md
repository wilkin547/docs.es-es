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
ms.openlocfilehash: c88770403d4c2abfb5ce99f44ea1bec1f8337545
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84279781"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a><span data-ttu-id="bfbfd-103">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="bfbfd-103">The XML Schema Definition Tool and XML Serialization</span></span>

<span data-ttu-id="bfbfd-104">La herramienta de definición de esquema XML ([Herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) se instala junto con las herramientas de .NET Framework como parte del kit de desarrollo de software (SDK) de Windows&reg;.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-104">The XML Schema Definition tool ([XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md)) is installed along with the .NET Framework tools as part of the Windows&reg; Software Development Kit (SDK).</span></span> <span data-ttu-id="bfbfd-105">La herramienta está diseñada para cumplir principalmente dos propósitos:</span><span class="sxs-lookup"><span data-stu-id="bfbfd-105">The tool is designed primarily for two purposes:</span></span>  
  
- <span data-ttu-id="bfbfd-106">Para crear archivos de clase C# o para crearlos de clase Visual Basic y que así cumplan con un lenguaje de definición de esquema XML (XSD) concreto.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-106">To generate either C# or Visual Basic class files that conform to a specific XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="bfbfd-107">La herramienta toma un Esquema XML como un argumento y genera un archivo que contiene varias clases que cuando se serializa con <xref:System.Xml.Serialization.XmlSerializer>, cumpla al esquema.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-107">The tool takes an XML Schema as an argument and outputs a file that contains a number of classes that, when serialized with the <xref:System.Xml.Serialization.XmlSerializer>, conform to the schema.</span></span> <span data-ttu-id="bfbfd-108">Para más información sobre cómo usar la herramienta para generar clases que cumplan con un esquema en concreto, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfd-108">For information about how to use the tool to generate classes that conform to a specific schema, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
- <span data-ttu-id="bfbfd-109">Generar un documento de esquema XML de un archivo .dll o .exe.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-109">To generate an XML Schema document from a .dll file or .exe file.</span></span> <span data-ttu-id="bfbfd-110">Para ver el esquema de un conjunto de archivos que ha creado, o uno que se ha modificado con atributos, pase la DLL o el EXE como un argumento de la herramienta para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="bfbfd-110">To see the schema of a set of files that you have either created or one that has been modified with attributes, pass the DLL or EXE as an argument to the tool to generate the XML schema.</span></span> <span data-ttu-id="bfbfd-111">Para más información sobre cómo usar la herramienta para generar un documento de esquema XML a partir de un conjunto de clases, vea [Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML](xml-schema-def-tool-gen.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfd-111">For information about how to use the tool to generate an XML Schema Document from a set of classes, see [How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents](xml-schema-def-tool-gen.md).</span></span>  
  
<span data-ttu-id="bfbfd-112">Para más información sobre cómo usar la herramienta, vea [Herramienta de definición de esquema XML (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bfbfd-112">For more information about using the tool, see [XML Schema Definition Tool (Xsd.exe)](xml-schema-definition-tool-xsd-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbfd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfbfd-113">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="bfbfd-114">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="bfbfd-114">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="bfbfd-115">Herramienta de definición de esquema XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="bfbfd-115">XML Schema Definition Tool (Xsd.exe)</span></span>](xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="bfbfd-116">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="bfbfd-116">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="bfbfd-117">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="bfbfd-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
- [<span data-ttu-id="bfbfd-118">Cómo: Usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="bfbfd-118">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>](xml-schema-def-tool-gen.md)
- <span data-ttu-id="bfbfd-119">[Compatibilidad con enlaces del esquema XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bfbfd-119">[XML Schema Binding Support](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))</span></span>
