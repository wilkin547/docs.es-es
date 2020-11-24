---
title: Validación de esquema XML (XSD) con XmlSchemaSet
description: Aprenda a validar documentos XML en un esquema del lenguaje de definición de esquema XML (XSD) con una clase XmlSchemaSet en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 9e1d4b7e8c805436c32d2ae7b340ee251741f4a1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824576"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="62585-103">Validación de esquema XML (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="62585-103">XML schema (XSD) validation with XmlSchemaSet</span></span>

<span data-ttu-id="62585-104">Los documentos XML se pueden validar con un esquema del lenguaje de definición de esquemas (XSD) en un <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="62585-104">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validate-xml-documents"></a><span data-ttu-id="62585-105">Validación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="62585-105">Validate XML documents</span></span>  
 <span data-ttu-id="62585-106">El método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> valida los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="62585-106">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="62585-107">Para validar un documento XML, construya un objeto <xref:System.Xml.XmlReaderSettings> que contiene un esquema XSD con el que validar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="62585-107">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62585-108">El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que facilitan el proceso de validar un árbol XML en un archivo XSD cuando se utiliza [LINQ to XML (C#)](../../linq/linq-xml-overview.md) y [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="62585-108">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span></span> <span data-ttu-id="62585-109">Para obtener más información sobre cómo validar documentos XML con LINQ to XML, vea [Procedimiento para realizar validaciones con XSD (LINQ to XML) (C#)](../../linq/validate-xsd.md) y [Cómo: Validar con XSD (LINQ to XML) (Visual Basic)](../../linq/validate-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="62585-109">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../linq/validate-xsd.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../linq/validate-xsd.md).</span></span>
  
 <span data-ttu-id="62585-110">Es posible agregar un esquema en particular o un conjunto de esquemas (como un <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> pasando uno de ellos como parámetro del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="62585-110">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="62585-111">Cuando se valida un documento, el espacio de nombres de destino del documento debe coincidir con el espacio de nombres de destino del esquema que forma parte del conjunto.</span><span class="sxs-lookup"><span data-stu-id="62585-111">When validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="62585-112">El siguiente es un ejemplo de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="62585-112">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="62585-113">El siguiente es el esquema que valida el ejemplo del documento XML.</span><span class="sxs-lookup"><span data-stu-id="62585-113">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="62585-114">En el código de ejemplo siguiente, se agrega el esquema anterior a la propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A> del objeto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="62585-114">In the code example that follows, the schema above is added to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="62585-115">El objeto <xref:System.Xml.XmlReaderSettings> se pasa como parámetro del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>, el cual valida el documento XML anterior.</span><span class="sxs-lookup"><span data-stu-id="62585-115">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="62585-116">La propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> del objeto <xref:System.Xml.XmlReaderSettings> se establece en `Schema` para exigir la validación del documento XML por medio del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="62585-116">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="62585-117">Se agrega un <xref:System.Xml.Schema.ValidationEventHandler> al objeto <xref:System.Xml.XmlReaderSettings> para controlar cualquier evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> que inicien los errores encontrados durante el proceso de validación del documento XML y del esquema.</span><span class="sxs-lookup"><span data-stu-id="62585-117">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="62585-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="62585-118">See also</span></span>

- [<span data-ttu-id="62585-119">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="62585-119">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="62585-120">Trabajo con esquemas XML</span><span class="sxs-lookup"><span data-stu-id="62585-120">Working with XML Schemas</span></span>](working-with-xml-schemas.md)
