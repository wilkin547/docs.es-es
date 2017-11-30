---
title: Compatibilidad de tipos en las clases System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="63ea8-102">Compatibilidad de tipos en las clases System.Xml</span><span class="sxs-lookup"><span data-stu-id="63ea8-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="63ea8-103">En la versión 2.0 de .NET Framework, se han mejorado las clases XML principales para incluir características de compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="63ea8-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="63ea8-104">Las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> tienen características de compatibilidad de tipos, incluyendo la capacidad de realizar conversiones entre tipos de esquemas XML y tipos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="63ea8-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="63ea8-105">En la versión 2.0 de .NET Framework, se han mejorado las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.XPath.XPathNavigator> para incluir características de compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="63ea8-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
-   <span data-ttu-id="63ea8-106">El <xref:System.Xml.XmlReader> y <xref:System.Xml.XPath.XPathNavigator> clases cada incluyen un **SchemaInfo** propiedad que devuelve la información de esquema en un nodo.</span><span class="sxs-lookup"><span data-stu-id="63ea8-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
-   <span data-ttu-id="63ea8-107">El **ReadContentAs** y **ReadElementContentAs** y métodos en la <xref:System.Xml.XmlReader> clase leer un valor de texto y convertirlo en un valor CLR en una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="63ea8-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
-   <span data-ttu-id="63ea8-108">El método <xref:System.Xml.XmlWriter.WriteValue%2A> de la clase <xref:System.Xml.XmlWriter> convierte un tipo CLR en un tipo de esquema XML cuando escribe XML.</span><span class="sxs-lookup"><span data-stu-id="63ea8-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
-   <span data-ttu-id="63ea8-109">El **ValueAs** y <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> propiedades en la <xref:System.Xml.XPath.XPathNavigator> clase devuelve un valor de nodo y lo convierten en un valor CLR en una única llamada al método.</span><span class="sxs-lookup"><span data-stu-id="63ea8-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63ea8-110">En la versión 1.0 de .NET Framework, se necesitaba la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="63ea8-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63ea8-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="63ea8-111">In This Section</span></span>  
 [<span data-ttu-id="63ea8-112">Asignar tipos de datos XML a tipos CLR</span><span class="sxs-lookup"><span data-stu-id="63ea8-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="63ea8-113">Describe las asignaciones predeterminadas de tipos de datos XML en tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="63ea8-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="63ea8-114">Notas de implementación de compatibilidad de tipo XML</span><span class="sxs-lookup"><span data-stu-id="63ea8-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="63ea8-115">Explica algunos de los detalles de la implementación de la compatibilidad de tipos.</span><span class="sxs-lookup"><span data-stu-id="63ea8-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="63ea8-116">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="63ea8-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="63ea8-117">Describe cómo utilizar la clase <xref:System.Xml.XmlConvert> para realizar la conversión entre esquemas XML y tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="63ea8-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="63ea8-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="63ea8-118">Related Sections</span></span>  
 [<span data-ttu-id="63ea8-119">Acceso a fuertemente tipados datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="63ea8-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
