---
title: Comparación de objetos mediante XmlNameTable
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
ms.openlocfilehash: 0dd68e8c9beadf26f858a4a5100e2824bbbd4a19
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292038"
---
# <a name="object-comparison-using-xmlnametable"></a><span data-ttu-id="45f26-102">Comparación de objetos mediante XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="45f26-102">Object Comparison Using XmlNameTable</span></span>
<span data-ttu-id="45f26-103">Cuando se crean **XmlDocuments**, se crea una tabla de nombres específicamente para dichos documentos.</span><span class="sxs-lookup"><span data-stu-id="45f26-103">**XmlDocuments**, when created, have a name table created specifically for that document.</span></span> <span data-ttu-id="45f26-104">Cuando se carga XML en el documento o cuando se crean elementos o atributos, los nombres de los atributos y elementos se colocan en la tabla **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="45f26-104">When XML is loaded into the document, or new elements or attributes are created, the attribute and element names are put into the **XmlNameTable**.</span></span> <span data-ttu-id="45f26-105">También puede crear una clase **XmlDocument** mediante una tabla **NameTable** existente de otro documento.</span><span class="sxs-lookup"><span data-stu-id="45f26-105">You can also create an **XmlDocument** using an existing **NameTable** from another document.</span></span> <span data-ttu-id="45f26-106">Cuando se crean **XmlDocuments** con el constructor que acepta un parámetro **XmlNameTable**, el documento tiene acceso a los nombres de nodo, espacios de nombres y prefijos ya almacenados en la tabla **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="45f26-106">When **XmlDocuments** are created with the constructor that takes an **XmlNameTable** parameter, the document has access to the node names, namespaces, and prefixes already stored in the **XmlNameTable**.</span></span> <span data-ttu-id="45f26-107">Independientemente de cómo se carguen los nombres en la tabla, una vez que se almacenan en ella, pueden compararse rápidamente mediante la comparación de objetos, en lugar de a través de la comparación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="45f26-107">Regardless of how the name table is loaded with names, once the names are stored in the table, names can be compared quickly using object comparison instead of string comparison.</span></span> <span data-ttu-id="45f26-108">También se pueden agregar cadenas a la tabla de nombres con <xref:System.Xml.NameTable.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="45f26-108">Strings can also be added to the name table using the <xref:System.Xml.NameTable.Add%2A>.</span></span> <span data-ttu-id="45f26-109">En el ejemplo de código siguiente se muestra una tabla de nombres creada y la cadena **MyString** que se agrega a la tabla.</span><span class="sxs-lookup"><span data-stu-id="45f26-109">The following code sample shows a name table being created and the string **MyString** being added to the table.</span></span> <span data-ttu-id="45f26-110">Después, se crea una clase **XmlDocument** con dicha tabla y los nombres de los elementos y atributos de **Myfile.xml** se agregan a la tabla de nombres existente.</span><span class="sxs-lookup"><span data-stu-id="45f26-110">After that, an **XmlDocument** is created using that table, and the element and attribute names in **Myfile.xml** are added to the existing name table.</span></span>  
  
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
  
 <span data-ttu-id="45f26-111">En el ejemplo de código siguiente se muestra la creación de un documento, se agregan dos elementos nuevos al documento, que también se agregan a la tabla de nombres de documento, y se comparan objetos en los nombres.</span><span class="sxs-lookup"><span data-stu-id="45f26-111">The following code example shows the creation of a document, two new elements being added to the document, which also adds them to the document name table, and the object comparison on the names.</span></span>  
  
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
  
 <span data-ttu-id="45f26-112">La situación anterior de una tabla de nombres que se pasa entre dos documentos es habitual cuando se procesa el mismo tipo de documento varias veces, como documentos de pedidos en un sitio de comercio electrónico, que se ajustan a un esquema XSD o DTD, y se repiten las mismas cadenas.</span><span class="sxs-lookup"><span data-stu-id="45f26-112">The above scenario of a name table passed between two documents is typical when the same type of document is being processed repeatedly, such as order documents at an ecommerce site, which conform to an XML Schema definition language (XSD) schema or document type definition (DTD) and the same strings are repeated.</span></span> <span data-ttu-id="45f26-113">Si se utiliza la misma tabla de nombres, se mejora la eficacia del sistema, puesto que el mismo nombre de elemento aparece en varios documentos.</span><span class="sxs-lookup"><span data-stu-id="45f26-113">Using the same name table gives a performance improvement, as the same element name occurs in multiple documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f26-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="45f26-114">See also</span></span>

- [<span data-ttu-id="45f26-115">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="45f26-115">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
