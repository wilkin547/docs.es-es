---
title: "Validación de esquema XML (XSD) con XmlSchemaSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 99e2f66a1aedafe316ab65ae302113ea553146ed
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="1a153-102">Validación de esquema XML (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="1a153-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="1a153-103">Los documentos XML se pueden validar con un esquema del lenguaje de definición de esquemas (XSD) en un <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="1a153-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="1a153-104">Validación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="1a153-104">Validating XML Documents</span></span>  
 <span data-ttu-id="1a153-105">El método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> valida los documentos XML.</span><span class="sxs-lookup"><span data-stu-id="1a153-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="1a153-106">Para validar un documento XML, construya un objeto <xref:System.Xml.XmlReaderSettings> que contiene un esquema XSD con el que validar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="1a153-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a153-107">El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que facilitan el proceso de validar un árbol XML en un archivo XSD si se utiliza [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="1a153-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="1a153-108">Para obtener más información sobre cómo validar documentos XML con LINQ to XML, vea [Cómo validar con XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).</span><span class="sxs-lookup"><span data-stu-id="1a153-108">For more information on validating XML documents with LINQ to XML, see [How to: Validate Using XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).</span></span>  
  
 <span data-ttu-id="1a153-109">Es posible agregar un esquema en particular o un conjunto de esquemas (como un <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> pasando uno de ellos como parámetro del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="1a153-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="1a153-110">Observe que cuando se valida un documento, el espacio de nombres de destino del documento debe coincidir con el espacio de nombres de destino del esquema que forma parte del conjunto.</span><span class="sxs-lookup"><span data-stu-id="1a153-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="1a153-111">El siguiente es un ejemplo de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="1a153-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="1a153-112">El siguiente es el esquema que valida el ejemplo del documento XML.</span><span class="sxs-lookup"><span data-stu-id="1a153-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="1a153-113">En el código de ejemplo siguiente, se agrega el esquema anterior a la propiedad <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> del objeto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="1a153-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="1a153-114">El objeto <xref:System.Xml.XmlReaderSettings> se pasa como parámetro del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>, el cual valida el documento XML anterior.</span><span class="sxs-lookup"><span data-stu-id="1a153-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="1a153-115">La propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> del objeto <xref:System.Xml.XmlReaderSettings> se establece en `Schema` para exigir la validación del documento XML por medio del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="1a153-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="1a153-116">Se agrega un <xref:System.Xml.Schema.ValidationEventHandler> al objeto <xref:System.Xml.XmlReaderSettings> para controlar cualquier evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> que inicien los errores encontrados durante el proceso de validación del documento XML y del esquema.</span><span class="sxs-lookup"><span data-stu-id="1a153-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1a153-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a153-117">See Also</span></span>  
 [<span data-ttu-id="1a153-118">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="1a153-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="1a153-119">Trabajo con esquemas XML</span><span class="sxs-lookup"><span data-stu-id="1a153-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
