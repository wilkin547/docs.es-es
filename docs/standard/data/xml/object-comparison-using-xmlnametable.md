---
title: "Comparación de objetos mediante XmlNameTable"
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
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd1a3bad69499b4804299adecabad3a43b5eab1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="548f4-102">Comparación de objetos mediante XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="548f4-102">Object Comparison Using XmlNameTable</span></span>
<span data-ttu-id="548f4-103">**XmlDocuments**, cuando se crea, tiene una tabla de nombres creada específicamente para dichos documentos.</span><span class="sxs-lookup"><span data-stu-id="548f4-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="548f4-104">Cuando se carga XML en el documento, o se crean nuevos elementos o atributos, los nombres de atributos y elementos se colocan en la **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="548f4-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="548f4-105">También puede crear un **XmlDocument** mediante existente **NameTable** desde otro documento.</span><span class="sxs-lookup"><span data-stu-id="548f4-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="548f4-106">Cuando **XmlDocuments** se crean con el constructor que toma un **XmlNameTable** parámetro, el documento tiene acceso a los nombres de nodo, espacios de nombres y prefijos ya almacenados en la  **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="548f4-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="548f4-107">Independientemente de cómo se carguen los nombres en la tabla, una vez que se almacenan en ella, pueden compararse rápidamente mediante la comparación de objetos, en lugar de a través de la comparación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="548f4-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="548f4-108">Las cadenas también pueden agregarse a la tabla de nombres mediante el <xref:System.Xml.NameTable.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="548f4-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="548f4-109">El ejemplo de código siguiente muestra una tabla de nombres creada y la cadena **MyString** se agregan a la tabla.</span><span class="sxs-lookup"><span data-stu-id="548f4-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="548f4-110">Después de eso, una **XmlDocument** se crea usando esa tabla y los nombres de elemento y atributo en **Myfile.xml** se agregan a la tabla de nombres existente.</span><span class="sxs-lookup"><span data-stu-id="548f4-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 <span data-ttu-id="548f4-111">En el ejemplo de código siguiente se muestra la creación de un documento, se agregan dos elementos nuevos al documento, que también se agregan a la tabla de nombres de documento, y se comparan objetos en los nombres.</span><span class="sxs-lookup"><span data-stu-id="548f4-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 <span data-ttu-id="548f4-112">La situación anterior de una tabla de nombres que se pasa entre dos documentos es habitual cuando se procesa el mismo tipo de documento varias veces, como documentos de pedidos en un sitio de comercio electrónico, que se ajustan a un esquema XSD o DTD, y se repiten las mismas cadenas.</span><span class="sxs-lookup"><span data-stu-id="548f4-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="548f4-113">Si se utiliza la misma tabla de nombres, se mejora la eficacia del sistema, puesto que el mismo nombre de elemento aparece en varios documentos.</span><span class="sxs-lookup"><span data-stu-id="548f4-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548f4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="548f4-114">See Also</span></span>  
 [<span data-ttu-id="548f4-115">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="548f4-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
