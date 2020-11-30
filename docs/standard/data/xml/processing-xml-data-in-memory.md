---
title: Procesamiento de datos XML en memoria
ms.date: 03/30/2017
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
ms.openlocfilehash: 878e008f5c7c3a018389e8666263269162989812
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686922"
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="7a8b1-102">Procesamiento de datos XML en memoria</span><span class="sxs-lookup"><span data-stu-id="7a8b1-102">Processing XML Data In-Memory</span></span>

<span data-ttu-id="7a8b1-103">Microsoft .NET Framework incluye tres modelos para el procesamiento de datos XML: la clase <xref:System.Xml.XmlDocument>, la clase <xref:System.Xml.XPath.XPathDocument> y [LINQ to XML (C#)](../../linq/linq-xml-overview.md) y [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7a8b1-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML (C#)](../../linq/linq-xml-overview.md) and [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md).</span></span>  
  
 <span data-ttu-id="7a8b1-104">La clase <xref:System.Xml.XmlDocument> implementa el nivel 1 principal del Modelo de objetos de documento (DOM) y las recomendaciones principales del nivel 2 del DOM del W3C.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="7a8b1-105">El DOM es una representación de árbol en memoria (caché) de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="7a8b1-106">Con <xref:System.Xml.XmlDocument> y  sus clases relacionadas, puede construir documentos XML, cargar datos y tener acceso a ellos, modificar datos y guardar cambios.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="7a8b1-107">La clase <xref:System.Xml.XPath.XPathDocument> es un almacén de datos en memoria y de solo lectura que se basa en el modelo de datos XPath.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="7a8b1-108">La clase <xref:System.Xml.XPath.XPathNavigator> ofrece diversas opciones de edición y capacidades de navegación utilizando un modelo de cursor sobre documentos XML contenidos en la clase <xref:System.Xml.XPath.XPathDocument> de solo lectura, así como en la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="7a8b1-109">[LINQ to XML](../../linq/linq-xml-overview.md) es un modelo que incorpora .NET Framework versión 3.5 para el procesamiento de datos XML.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-109">[LINQ to XML](../../linq/linq-xml-overview.md) is a model introduced in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="7a8b1-110">Es un modelo en memoria que usa [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="7a8b1-110">It's an in-memory model that leverages [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).</span></span> <span data-ttu-id="7a8b1-111">LINQ amplía la sintaxis del lenguaje C# y Visual Basic para proporcionar nuevas capacidades de consulta.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a8b1-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7a8b1-112">In This Section</span></span>  

 [<span data-ttu-id="7a8b1-113">Procesamiento de datos XML con el modelo DOM</span><span class="sxs-lookup"><span data-stu-id="7a8b1-113">Process XML Data Using the DOM Model</span></span>](process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="7a8b1-114">Describe el uso de <xref:System.Xml.XmlDocument> y sus clases relacionadas para procesar datos XML.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="7a8b1-115">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="7a8b1-115">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="7a8b1-116">Describe el uso de las clases <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> y <xref:System.Xml.XPath.XPathNavigator> para procesar datos XML.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="7a8b1-117">Procesamiento de datos XML utilizando LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7a8b1-117">Process XML Data Using LINQ to XML</span></span>](process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="7a8b1-118">Propociona una descripción general acerca de LINQ to XML, así como vínculos que hacen referencia a la documentación de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="7a8b1-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a8b1-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7a8b1-119">Related Sections</span></span>  

 [<span data-ttu-id="7a8b1-120">Documentos y datos XML</span><span class="sxs-lookup"><span data-stu-id="7a8b1-120">XML Documents and Data</span></span>](index.md)
