---
title: Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 2bbdced0f984b653a58afba9685683e8c0891271
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389796"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="d1109-102">Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="d1109-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="d1109-103">La herramienta XML Schema Definition (Xsd.exe) le permite generar un esquema XML que describe una clase o generar la clase definida por un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="d1109-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="d1109-104">Los procedimientos siguientes muestran cómo realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="d1109-104">The following procedures show how to perform these operations.</span></span>

<span data-ttu-id="d1109-105">La herramienta de definición de esquema XML (Xsd.exe) suele estar en la siguiente ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="d1109-105">The XML Schema Definition tool (Xsd.exe) usually can be found in the following path:</span></span>\
<span data-ttu-id="d1109-106">_C:\\Archivos de programa (x86)\\Microsoft SDKs\\Windows\\{versión}\\bin\\NETFX {versión} Tools\\_</span><span class="sxs-lookup"><span data-stu-id="d1109-106">_C:\\Program Files (x86)\\Microsoft SDKs\\Windows\\{version}\\bin\\NETFX {version} Tools\\_</span></span>

### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="d1109-107">Para generar clases que cumplen con un esquema concreto</span><span class="sxs-lookup"><span data-stu-id="d1109-107">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="d1109-108">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d1109-108">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="d1109-109">Pasar el esquema XML como un argumento a la herramienta XML Schema Definition, que crea un conjunto de clases con las que precisamente coinciden el Esquema XML, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1109-109">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="d1109-110">La herramienta solo puede procesar esquemas que hagan referencia a la especificación de World Wide Web Consortium XML del 16 de marzo de 2001.</span><span class="sxs-lookup"><span data-stu-id="d1109-110">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="d1109-111">En otras palabras, el espacio de nombres del esquema XML debe ser "http://www.w3.org/2001/XMLSchema" como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1109-111">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. <span data-ttu-id="d1109-112">Modifique las clases con métodos, propiedades o campos, como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d1109-112">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="d1109-113">Para más información sobre cómo modificar una clase con atributos, vea [Controlar la serialización XML mediante atributos](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) y [Atributos que controlan la serialización SOAP codificada](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="d1109-113">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="d1109-114">Es a menudo útil para examinar el esquema de la secuencia XML que se genera cuando se serializan las instancias de una clase (o clases).</span><span class="sxs-lookup"><span data-stu-id="d1109-114">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="d1109-115">Por ejemplo, podría publicar su esquema para que otros lo utilicen o podría compararlo con un esquema con el que está intentando lograr la conformidad.</span><span class="sxs-lookup"><span data-stu-id="d1109-115">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="d1109-116">Para generar un documento de esquema XML de un conjunto de clases</span><span class="sxs-lookup"><span data-stu-id="d1109-116">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="d1109-117">Compile la clase o clases en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="d1109-117">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="d1109-118">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d1109-118">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="d1109-119">Pasar el archivo DLL como un argumento a Xsd.exe, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d1109-119">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="d1109-120">Se escribirá el esquema (o esquemas), comenzando con "schema0.xsd" del nombre.</span><span class="sxs-lookup"><span data-stu-id="d1109-120">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1109-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1109-121">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="d1109-122">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="d1109-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="d1109-123">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="d1109-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="d1109-124">Herramienta de definición de esquema XML (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="d1109-124">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="d1109-125">Cómo: para serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="d1109-125">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="d1109-126">Cómo: para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="d1109-126">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
