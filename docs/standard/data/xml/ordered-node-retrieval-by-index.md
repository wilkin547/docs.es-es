---
title: "Recuperaci&#243;n de nodos ordenados por &#237;ndice | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Recuperaci&#243;n de nodos ordenados por &#237;ndice
DOM del W3C también describe una NodeList, que tiene la capacidad de controlar una lista de nodos ordenados, en contraposición al conjunto desordenado controlado por **XmlNamedNodeMap**.  La NodeList incluida en .NET Framework se denomina **XmlNodeList**.  Los métodos y propiedades que devuelve una **XmlNodeList** son los siguientes:  
  
-   XmlNode.ChildNodes  
  
-   XmlDocument.GetElementsByTagName  
  
-   XmlElement.GetElementsByTagName  
  
-   XmlNode.SelectNodes  
  
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
  
 Además de la propiedad **Count**, hay un método **GetEnumerator** que proporciona una forma de iteración del estilo de `foreach` sobre la colección de nodos de **XmlNodeList**.  En el código de ejemplo siguiente se muestra el uso de la instrucción `foreach`.  
  
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
  
 Para obtener más información acerca de los métodos y propiedades disponibles en **XmlNodeList**, vea [XmlNodeList \(Miembros\)](frlrfSystemXmlXmlNodeListMembersTopic).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)