---
title: Trabajo con esquemas XML
ms.date: 03/30/2017
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
ms.openlocfilehash: 0290cd31d9477d2c5a30a6efa907263fed137258
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675495"
---
# <a name="working-with-xml-schemas"></a><span data-ttu-id="909e7-102">Trabajo con esquemas XML</span><span class="sxs-lookup"><span data-stu-id="909e7-102">Working with XML Schemas</span></span>

<span data-ttu-id="909e7-103">Para definir la estructura de un documento XML, así como las relaciones de sus elementos, tipos de datos y restricciones de contenido, se utiliza una definición de tipo de documento (DTD) o esquema del lenguaje de definición de esquemas (XSD).</span><span class="sxs-lookup"><span data-stu-id="909e7-103">To define the structure of an XML document, as well as its element relationships, data types, and content constraints, you use a document type definition (DTD) or XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="909e7-104">Aunque se considera que un documento XML es correcto si cumple todos los requisitos sintácticos que define la recomendación del Lenguaje de marcado extensible (XML) 1.0 del W3C (World Wide Web Consortium), no se considera válido a menos que sea correcto y además cumpla las restricciones que define su DTD o esquema.</span><span class="sxs-lookup"><span data-stu-id="909e7-104">Although an XML document is considered to be well-formed if it meets all the syntactical requirements defined by the World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0 Recommendation, it is not considered valid unless it is both well-formed and conforms to the constraints defined by its DTD or schema.</span></span> <span data-ttu-id="909e7-105">Por lo tanto, aunque todos los documentos XML válidos sean correctos, no todos los documentos XML correctos son válidos.</span><span class="sxs-lookup"><span data-stu-id="909e7-105">Therefore, although all valid XML documents are well-formed, not all well-formed XML documents are valid.</span></span>  
  
 <span data-ttu-id="909e7-106">Para obtener más información acerca de XML, vea [XML 1.0 - W3C Recommendation](https://www.w3.org/TR/REC-xml/).</span><span class="sxs-lookup"><span data-stu-id="909e7-106">For more information about XML, see the [W3C XML 1.0 Recommendation](https://www.w3.org/TR/REC-xml/).</span></span> <span data-ttu-id="909e7-107">Para obtener más información sobre el esquema XML, vea las recomendaciones de la [Parte 1 del esquema XML de W3C: recomendación de estructuras](https://www.w3.org/TR/xmlschema-1/) y la [Parte 2 del esquema XML de W3C: recomendación de tipos de datos](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="909e7-107">For more information about XML Schema, see the [W3C XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/) and the [W3C XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="909e7-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="909e7-108">In This Section</span></span>  

 [<span data-ttu-id="909e7-109">Modelo de objetos de esquema XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="909e7-109">XML Schema Object Model (SOM)</span></span>](xml-schema-object-model-som.md)  
 <span data-ttu-id="909e7-110">Describe el Modelo de objetos de esquema (SOM) del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que incluye un conjunto de clases que le permiten leer un esquema del lenguaje de definición de esquemas (XSD) desde un archivo o crear un esquema en memoria mediante programación.</span><span class="sxs-lookup"><span data-stu-id="909e7-110">Discusses the Schema Object Model (SOM) in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that provides a set of classes that allows you to read a Schema definition language (XSD) schema from a file or programmatically create a schema in-memory.</span></span>  
  
 [<span data-ttu-id="909e7-111">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="909e7-111">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)  
 <span data-ttu-id="909e7-112">Describe la clase <xref:System.Xml.Schema.XmlSchemaSet> que es una caché en la que se pueden almacenar y validar esquemas XSD.</span><span class="sxs-lookup"><span data-stu-id="909e7-112">Discusses the <xref:System.Xml.Schema.XmlSchemaSet> class that is a cache where XSD schemas can be stored and validated.</span></span>  
  
 [<span data-ttu-id="909e7-113">Validación basada en inserción de XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="909e7-113">XmlSchemaValidator Push-Based Validation</span></span>](xmlschemavalidator-push-based-validation.md)  
 <span data-ttu-id="909e7-114">Describe la clase <xref:System.Xml.Schema.XmlSchemaValidator> que incluye un mecanismo eficiente y de alto rendimiento para validar datos XML con esquemas XSD mediante inserción.</span><span class="sxs-lookup"><span data-stu-id="909e7-114">Discusses the <xref:System.Xml.Schema.XmlSchemaValidator> class that provides an efficient, high-performance mechanism to validate XML data against XSD schemas in a push-based manner.</span></span>  
  
 [<span data-ttu-id="909e7-115">Deducción de esquema XML</span><span class="sxs-lookup"><span data-stu-id="909e7-115">Inferring an XML Schema</span></span>](inferring-an-xml-schema.md)  
 <span data-ttu-id="909e7-116">Describe cómo utilizar la clase <xref:System.Xml.Schema.XmlSchemaInference> para deducir un esquema XSD de la estructura de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="909e7-116">Discusses how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XSD schema from the structure of an XML document.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="909e7-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="909e7-117">Reference</span></span>  

 <span data-ttu-id="909e7-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="909e7-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="909e7-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="909e7-119">Related Sections</span></span>  

 [<span data-ttu-id="909e7-120">Validación de un documento XML en DOM</span><span class="sxs-lookup"><span data-stu-id="909e7-120">Validating an XML Document in the DOM</span></span>](validating-an-xml-document-in-the-dom.md)  
 <span data-ttu-id="909e7-121">Describe cómo validar el XML en el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="909e7-121">Discusses how to validate the XML in the Document Object Model (DOM).</span></span> <span data-ttu-id="909e7-122">Puede validarlo a medida que se carga en el DOM o validar un documento XML no validado previamente en el DOM.</span><span class="sxs-lookup"><span data-stu-id="909e7-122">You can validate the XML as it is loaded into the DOM, or validate a previously unvalidated XML document in the DOM.</span></span>  
  
 [<span data-ttu-id="909e7-123">Validación de esquemas con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="909e7-123">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="909e7-124">Describe cómo validar el XML que se está editando y por el que se está navegando utilizando la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="909e7-124">Discusses how to validate XML being navigated and edited using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
