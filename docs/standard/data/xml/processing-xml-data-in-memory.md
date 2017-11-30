---
title: Procesamiento de datos XML en memoria
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="2d78e-102">Procesamiento de datos XML en memoria</span><span class="sxs-lookup"><span data-stu-id="2d78e-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="2d78e-103">Microsoft .NET Framework incluye tres modelos para procesar datos XML: la <xref:System.Xml.XmlDocument> (clase), el <xref:System.Xml.XPath.XPathDocument> (clase), y [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="2d78e-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="2d78e-104">La clase <xref:System.Xml.XmlDocument> implementa el nivel 1 principal del Modelo de objetos de documento (DOM) y las recomendaciones principales del nivel 2 del DOM del W3C.</span><span class="sxs-lookup"><span data-stu-id="2d78e-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="2d78e-105">El DOM es una representación de árbol en memoria (caché) de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="2d78e-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="2d78e-106">Con <xref:System.Xml.XmlDocument> y  sus clases relacionadas, puede construir documentos XML, cargar datos y tener acceso a ellos, modificar datos y guardar cambios.</span><span class="sxs-lookup"><span data-stu-id="2d78e-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="2d78e-107">La clase <xref:System.Xml.XPath.XPathDocument> es un almacén de datos en memoria y de solo lectura que se basa en el modelo de datos XPath.</span><span class="sxs-lookup"><span data-stu-id="2d78e-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="2d78e-108">La clase <xref:System.Xml.XPath.XPathNavigator> ofrece diversas opciones de edición y capacidades de navegación utilizando un modelo de cursor sobre documentos XML contenidos en la clase <xref:System.Xml.XPath.XPathDocument> de solo lectura, así como en la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="2d78e-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="2d78e-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) es el nuevo modelo en .NET Framework versión 3.5 para procesar datos XML.</span><span class="sxs-lookup"><span data-stu-id="2d78e-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="2d78e-110">Es un modelo en memoria que aprovecha [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="2d78e-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="2d78e-111">LINQ amplía la sintaxis del lenguaje C# y Visual Basic para proporcionar nuevas capacidades de consulta.</span><span class="sxs-lookup"><span data-stu-id="2d78e-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d78e-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2d78e-112">In This Section</span></span>  
 [<span data-ttu-id="2d78e-113">Procesamiento de datos XML con el modelo DOM</span><span class="sxs-lookup"><span data-stu-id="2d78e-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="2d78e-114">Describe el uso de <xref:System.Xml.XmlDocument> y sus clases relacionadas para procesar datos XML.</span><span class="sxs-lookup"><span data-stu-id="2d78e-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="2d78e-115">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="2d78e-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="2d78e-116">Describe el uso de las clases <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> y <xref:System.Xml.XPath.XPathNavigator> para procesar datos XML.</span><span class="sxs-lookup"><span data-stu-id="2d78e-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="2d78e-117">Procesamiento de datos XML utilizando LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="2d78e-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="2d78e-118">Propociona una descripción general acerca de LINQ to XML, así como vínculos que hacen referencia a la documentación de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="2d78e-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2d78e-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2d78e-119">Related Sections</span></span>  
 [<span data-ttu-id="2d78e-120">Documentos y datos XML</span><span class="sxs-lookup"><span data-stu-id="2d78e-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
