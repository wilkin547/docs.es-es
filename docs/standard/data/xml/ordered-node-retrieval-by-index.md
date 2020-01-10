---
title: Recuperación de nodos ordenados por índice
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
ms.openlocfilehash: 72e866e43b556d8534024a219d924b1f372ed073
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710523"
---
# <a name="ordered-node-retrieval-by-index"></a>Recuperación de nodos ordenados por índice
En Document Object Model (DOM) XML del World Wide Web Consortium (W3C) también se describe un objeto NodeList, que tiene la capacidad de controlar una lista de nodos ordenados, en contraposición al conjunto desordenado controlado por **XmlNamedNodeMap**. El objeto NodeList incluido en Microsoft .NET Framework se denomina **XmlNodeList**. Los métodos y las propiedades que devuelve un objeto **XmlNodeList** son los siguientes:  
  
- XmlNode.ChildNodes  
  
- XmlDocument.GetElementsByTagName  
  
- XmlElement.GetElementsByTagName  
  
- XmlNode.SelectNodes  
  
 **XmlNodeList** tiene una propiedad **Count** que se puede utilizar para escribir bucles y recorrer en iteración los nodos de **XmlNodeList**, tal como se muestra en el ejemplo de código siguiente:  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{     
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}   
```  
  
 Además de la propiedad **Count**, hay un método **GetEnumerator** que proporciona una forma de iteración del estilo de `foreach` sobre la colección de nodos de **XmlNodeList**. En el código de ejemplo siguiente se muestra el uso de la instrucción `foreach`.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum          
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();    
     // Loop over the XmlNodeList using the enumerator ienum          
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 Para más información sobre los métodos y las propiedades disponibles en **XmlNodeList**, vea <xref:System.Xml.XmlNodeList>.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
