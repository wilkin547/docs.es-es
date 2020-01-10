---
title: Creación de documentos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: a12555a02b45a964ff7efcbe00e0d2cb8637474a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709990"
---
# <a name="xml-document-creation"></a><span data-ttu-id="d5ae5-102">Creación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="d5ae5-102">XML Document Creation</span></span>
<span data-ttu-id="d5ae5-103">Hay dos formas de crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="d5ae5-104">Una es crear una clase **XmlDocument** sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="d5ae5-105">La otra es crear una clase **XmlDocument** y pasarle una clase XmlNameTable como parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="d5ae5-106">En el ejemplo siguiente se muestra cómo crear una clase **XmlDocument** vacía sin utilizar parámetros.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="d5ae5-107">Una vez creado un documento, se pueden cargar datos desde una cadena, secuencia, dirección URL, sistema de lectura de texto o una clase derivada de **XmlReader** mediante el método **Load**.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="d5ae5-108">Existe también otro método de carga, el método **LoadXML**, que lee XML a partir de una cadena.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="d5ae5-109">Para obtener más información acerca de los diversos métodos **Load**, vea [Lectura de un documento XML en el DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="d5ae5-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="d5ae5-110">Hay una clase denominada **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="d5ae5-111">Esta clase es una tabla de objetos de cadena divididos en átomos.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="d5ae5-112">La tabla proporciona un medio eficaz para que el analizador XML utilice el mismo objeto de cadena para todos los nombres de elemento y atributo repetidos en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="d5ae5-113">Al crear un documento, se crea un objeto **XmlNameTable** automáticamente, como se muestra a continuación, y al cargar el documento se cargan los nombres de elemento y atributo.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="d5ae5-114">Si dispone ya de un documento con una tabla de nombres y dichos nombres serían útiles en otro documento, puede crear un documento nuevo mediante el método **Load**, que acepta una clase **XmlNameTable** como parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="d5ae5-115">Al crear el documento con este método, utiliza la clase **XmlNameTable** existente con todos los atributos y elementos ya cargados desde el otro documento.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="d5ae5-116">Se puede utilizar para comparar de forma eficaz nombres de elemento y atributo.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="d5ae5-117">Para obtener más información acerca de **XmlNameTable**, vea [Comparación de objetos mediante XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="d5ae5-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="d5ae5-118">Como referencia, vea <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="d5ae5-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ae5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5ae5-119">See also</span></span>

- [<span data-ttu-id="d5ae5-120">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="d5ae5-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
