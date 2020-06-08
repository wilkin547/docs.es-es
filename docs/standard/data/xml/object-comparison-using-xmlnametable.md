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
# <a name="object-comparison-using-xmlnametable"></a>Comparación de objetos mediante XmlNameTable
Cuando se crean **XmlDocuments**, se crea una tabla de nombres específicamente para dichos documentos. Cuando se carga XML en el documento o cuando se crean elementos o atributos, los nombres de los atributos y elementos se colocan en la tabla **XmlNameTable**. También puede crear una clase **XmlDocument** mediante una tabla **NameTable** existente de otro documento. Cuando se crean **XmlDocuments** con el constructor que acepta un parámetro **XmlNameTable**, el documento tiene acceso a los nombres de nodo, espacios de nombres y prefijos ya almacenados en la tabla **XmlNameTable**. Independientemente de cómo se carguen los nombres en la tabla, una vez que se almacenan en ella, pueden compararse rápidamente mediante la comparación de objetos, en lugar de a través de la comparación de cadenas. También se pueden agregar cadenas a la tabla de nombres con <xref:System.Xml.NameTable.Add%2A>. En el ejemplo de código siguiente se muestra una tabla de nombres creada y la cadena **MyString** que se agrega a la tabla. Después, se crea una clase **XmlDocument** con dicha tabla y los nombres de los elementos y atributos de **Myfile.xml** se agregan a la tabla de nombres existente.  
  
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
  
 En el ejemplo de código siguiente se muestra la creación de un documento, se agregan dos elementos nuevos al documento, que también se agregan a la tabla de nombres de documento, y se comparan objetos en los nombres.  
  
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
  
 La situación anterior de una tabla de nombres que se pasa entre dos documentos es habitual cuando se procesa el mismo tipo de documento varias veces, como documentos de pedidos en un sitio de comercio electrónico, que se ajustan a un esquema XSD o DTD, y se repiten las mismas cadenas. Si se utiliza la misma tabla de nombres, se mejora la eficacia del sistema, puesto que el mismo nombre de elemento aparece en varios documentos.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
