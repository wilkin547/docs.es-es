---
title: "Creación de documentos XML"
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="e2923-102">Creación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="e2923-102">XML Document Creation</span></span>
<span data-ttu-id="e2923-103">Hay dos formas de crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e2923-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="e2923-104">Es una manera de crear un **XmlDocument** sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="e2923-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="e2923-105">El otro mecanismo consiste en crear un **XmlDocument** y pasarle una XmlNameTable como parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2923-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="e2923-106">En el ejemplo siguiente se muestra cómo crear una nueva y vacía **XmlDocument** sin ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2923-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="e2923-107">Una vez que se crea un documento, puede cargarlo con datos de una cadena, secuencia, dirección URL, el lector de texto, o un **XmlReader** deriva la clase utilizando el **cargar** método.</span><span class="sxs-lookup"><span data-stu-id="e2923-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="e2923-108">También hay otro método de carga, el **LoadXML** método, que lee XML desde una cadena.</span><span class="sxs-lookup"><span data-stu-id="e2923-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="e2923-109">Para obtener más información acerca de los diversos **carga** métodos, vea [leer un documento XML en el DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="e2923-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="e2923-110">Hay una clase denominada el **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="e2923-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="e2923-111">Esta clase es una tabla de objetos de cadena divididos en átomos.</span><span class="sxs-lookup"><span data-stu-id="e2923-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="e2923-112">La tabla proporciona un medio eficaz para que el analizador XML utilice el mismo objeto de cadena para todos los nombres de elemento y atributo repetidos en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e2923-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="e2923-113">Un **XmlNameTable** se crea automáticamente cuando un documento se crea como se indicó anteriormente y se carga con nombres de atributo y elemento cuando se carga el documento.</span><span class="sxs-lookup"><span data-stu-id="e2923-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="e2923-114">Si ya tiene un documento con una tabla de nombres y dichos nombres serían útiles en otro documento, puede crear un documento nuevo mediante el **carga** método que toma un **XmlNameTable** como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2923-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="e2923-115">Cuando se crea el documento con este método, utiliza existente **XmlNameTable** con todos los atributos y elementos ya cargados desde el otro documento.</span><span class="sxs-lookup"><span data-stu-id="e2923-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="e2923-116">Se puede utilizar para comparar de forma eficaz nombres de elemento y atributo.</span><span class="sxs-lookup"><span data-stu-id="e2923-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="e2923-117">Para obtener más información sobre la **XmlNameTable**, consulte [comparación de objetos mediante XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="e2923-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="e2923-118">Como referencia, vea <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="e2923-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2923-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2923-119">See Also</span></span>  
 [<span data-ttu-id="e2923-120">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="e2923-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
