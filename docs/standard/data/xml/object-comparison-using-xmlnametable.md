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
# <a name="object-comparison-using-xmlnametable"></a>Comparación de objetos mediante XmlNameTable
**XmlDocuments**, cuando se crea, tiene una tabla de nombres creada específicamente para dichos documentos. Cuando se carga XML en el documento, o se crean nuevos elementos o atributos, los nombres de atributos y elementos se colocan en la **XmlNameTable**. También puede crear un **XmlDocument** mediante existente **NameTable** desde otro documento. Cuando **XmlDocuments** se crean con el constructor que toma un **XmlNameTable** parámetro, el documento tiene acceso a los nombres de nodo, espacios de nombres y prefijos ya almacenados en la  **XmlNameTable**. Independientemente de cómo se carguen los nombres en la tabla, una vez que se almacenan en ella, pueden compararse rápidamente mediante la comparación de objetos, en lugar de a través de la comparación de cadenas. Las cadenas también pueden agregarse a la tabla de nombres mediante el <xref:System.Xml.NameTable.Add%2A>. El ejemplo de código siguiente muestra una tabla de nombres creada y la cadena **MyString** se agregan a la tabla. Después de eso, una **XmlDocument** se crea usando esa tabla y los nombres de elemento y atributo en **Myfile.xml** se agregan a la tabla de nombres existente.  
  
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
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
