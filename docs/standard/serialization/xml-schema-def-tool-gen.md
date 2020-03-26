---
title: Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 4c6996e2279693cf96c826741869d72007cf81cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249557"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a><span data-ttu-id="dd2c2-102">Procedimiento para usar la herramienta de definición de esquema XML para generar clases y documentos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="dd2c2-102">How to: Use the XML Schema Definition Tool to Generate Classes and XML Schema Documents</span></span>
<span data-ttu-id="dd2c2-103">La herramienta XML Schema Definition (Xsd.exe) le permite generar un esquema XML que describe una clase o generar la clase definida por un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-103">The XML Schema Definition tool (Xsd.exe) allows you to generate an XML schema that describes a class or to generate the class defined by an XML schema.</span></span> <span data-ttu-id="dd2c2-104">Los procedimientos siguientes muestran cómo realizar estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-104">The following procedures show how to perform these operations.</span></span>  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a><span data-ttu-id="dd2c2-105">Para generar clases que cumplen con un esquema concreto</span><span class="sxs-lookup"><span data-stu-id="dd2c2-105">To generate classes that conform to a specific schema</span></span>  
  
1. <span data-ttu-id="dd2c2-106">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-106">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="dd2c2-107">Pasar el esquema XML como un argumento a la herramienta XML Schema Definition, que crea un conjunto de clases con las que precisamente coinciden el Esquema XML, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd2c2-107">Pass the XML Schema as an argument to the XML Schema Definition tool, which creates a set of classes that are precisely matched to the XML Schema, for example:</span></span>  
  
    ```console  
    xsd mySchema.xsd  
    ```  
  
     <span data-ttu-id="dd2c2-108">La herramienta solo puede procesar esquemas que hagan referencia a la especificación de World Wide Web Consortium XML del 16 de marzo de 2001.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-108">The tool can only process schemas that reference the World Wide Web Consortium XML specification of March 16, 2001.</span></span> <span data-ttu-id="dd2c2-109">En otras palabras, el espaciohttp://www.w3.org/2001/XMLSchemade nombres de esquema XML debe ser " " como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-109">In other words, the XML Schema namespace must be "http://www.w3.org/2001/XMLSchema" as shown in the following example.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema" />  
    ```  
  
3. <span data-ttu-id="dd2c2-110">Modifique las clases con métodos, propiedades o campos, como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-110">Modify the classes with methods, properties, or fields, as necessary.</span></span> <span data-ttu-id="dd2c2-111">Para más información sobre cómo modificar una clase con atributos, vea [Controlar la serialización XML mediante atributos](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) y [Atributos que controlan la serialización SOAP codificada](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="dd2c2-111">For more information about modifying a class with attributes, see [Controlling XML Serialization Using Attributes](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) and [Attributes That Control Encoded SOAP Serialization](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).</span></span>  
  
 <span data-ttu-id="dd2c2-112">Es a menudo útil para examinar el esquema de la secuencia XML que se genera cuando se serializan las instancias de una clase (o clases).</span><span class="sxs-lookup"><span data-stu-id="dd2c2-112">It is often useful to examine the schema of the XML stream that is generated when instances of a class (or classes) are serialized.</span></span> <span data-ttu-id="dd2c2-113">Por ejemplo, podría publicar su esquema para que otros lo utilicen o podría compararlo con un esquema con el que está intentando lograr la conformidad.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-113">For example, you might publish your schema for others to use, or you might compare it to a schema with which you are trying to achieve conformity.</span></span>  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a><span data-ttu-id="dd2c2-114">Para generar un documento de esquema XML de un conjunto de clases</span><span class="sxs-lookup"><span data-stu-id="dd2c2-114">To generate an XML Schema document from a set of classes</span></span>  
  
1. <span data-ttu-id="dd2c2-115">Compile la clase o clases en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-115">Compile the class or classes into a DLL.</span></span>  
  
2. <span data-ttu-id="dd2c2-116">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-116">Open a command prompt.</span></span>  
  
3. <span data-ttu-id="dd2c2-117">Pasar el archivo DLL como un argumento a Xsd.exe, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd2c2-117">Pass the DLL as an argument to Xsd.exe, for example:</span></span>  
  
    ```console  
    xsd MyFile.dll  
    ```  
  
     <span data-ttu-id="dd2c2-118">Se escribirá el esquema (o esquemas), comenzando con "schema0.xsd" del nombre.</span><span class="sxs-lookup"><span data-stu-id="dd2c2-118">The schema (or schemas) will be written, beginning with the name "schema0.xsd".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2c2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd2c2-119">See also</span></span>

- <xref:System.Data.DataSet>
- [<span data-ttu-id="dd2c2-120">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="dd2c2-120">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="dd2c2-121">Introducir la serialización XML</span><span class="sxs-lookup"><span data-stu-id="dd2c2-121">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="dd2c2-122">XML Schema Definition Tool (Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="dd2c2-122">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="dd2c2-123">Procedimiento para serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="dd2c2-123">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="dd2c2-124">Procedimiento para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="dd2c2-124">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
