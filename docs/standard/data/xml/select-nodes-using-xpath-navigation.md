---
title: Selección de nodos con la navegación XPath
description: Aprenda a seleccionar nodos XML en .NET. Use métodos Document Object Model (DOM) que le permitan utilizar la navegación del lenguaje de ruta XML (XPath) para consultar información de DOM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: b8a67d1fd508d0674d9230d4b934071a15669599
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829250"
---
# <a name="select-nodes-using-xpath-navigation"></a>Selección de nodos con la navegación XPath
El Modelo de objetos del documento (DOM) XML contiene métodos que le permiten utilizar la navegación del lenguaje de ruta XML (XPath) para consultar información en el DOM. Puede utilizar XPath para buscar un solo nodo específico o para buscar todos los nodos que cumplen algunos criterios.  
  
## <a name="xpath-select-methods"></a>Métodos de selección de XPath  
 Las clases DOM incluyen dos métodos para la selección de XPath: <xref:System.Xml.XmlNode.SelectSingleNode%2A> y <xref:System.Xml.XmlNode.SelectNodes%2A>. El método <xref:System.Xml.XmlNode.SelectSingleNode%2A> devuelve el primer nodo que cumple los criterios de selección. El método <xref:System.Xml.XmlNode.SelectNodes%2A> devuelve un <xref:System.Xml.XmlNodeList> que contiene los nodos coincidentes.  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Xml.XmlNode.SelectSingleNode%2A> para seleccionar el primer nodo `book` en el que el apellido del autor cumple los criterios especificados. El archivo bookstore.xml (que se proporciona al final de este tema) se utiliza como archivo de entrada.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 En el ejemplo siguiente, el método <xref:System.Xml.XmlNode.SelectNodes%2A> se utiliza para seleccionar todos los nodos de libro cuyo precio es mayor que una cantidad dada. A continuación, el precio de cada libro de la lista seleccionada se reduce en un diez por ciento mediante programación. Por último, el archivo actualizado se escribe en la consola. El archivo bookstore.xml (que se proporciona al final de este tema) se utiliza como archivo de entrada.  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 Los ejemplos anteriores comienzan la consulta XPath en el elemento de documento. Al establecer el punto de inicio de la consulta XPath, se establece el nodo de contexto, que es el punto de inicio de la consulta XPath. Si no desea comenzar en el elemento de documento, sino en el primer elemento secundario del elemento de documento, puede codificar la instrucción SELECT como se indica a continuación:  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 Todos los objetos <xref:System.Xml.XmlNodeList> se sincronizan con el documento subyacente. Por lo tanto, si itera a través de la lista de nodos y modifica el valor de un nodo, ese nodo también se actualiza en el documento del que proviene. En el ejemplo anterior observe que cuando se modifica un nodo en el objeto <xref:System.Xml.XmlNodeList> seleccionado, se modifica también el documento subyacente.  
  
> [!NOTE]
> Cuando se modifica el documento subyacente, es aconsejable volver a ejecutar la selección. Si el nodo modificado puede provocar que el nodo se agregue a la lista de nodos cuando antes no estaba, o que se quite de la lista de nodos, no hay ninguna garantía de que la lista de nodos sea precisa.  
  
## <a name="namespaces-in-xpath-expressions"></a>Espacios de nombres en expresiones XPath  
 Las expresiones XPath pueden incluir espacios de nombres. La resolución de espacios de nombres es compatible con <xref:System.Xml.XmlNamespaceManager>. Si la expresión XPath incluye un prefijo, el par del prefijo y el identificador URI de espacio de nombres se debe agregar a <xref:System.Xml.XmlNamespaceManager>, y <xref:System.Xml.XmlNamespaceManager> se pasa al método <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> o <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>. Observe que los ejemplos de código anteriores utilizan <xref:System.Xml.XmlNamespaceManager> para resolver el espacio de nombres del documento bookstore.xml.  
  
> [!NOTE]
> Si la expresión XPath no incluye un prefijo, se asume que el identificador uniforme de recursos (URI) de espacio de nombres es el espacio de nombres vacío. Si el XML incluye un espacio de nombres predeterminado, deberá agregar también un prefijo y un identificador URI de espacio de nombres a <xref:System.Xml.XmlNamespaceManager>; de lo contrario, no se seleccionará ningún nodo.  
  
#### <a name="input-file"></a>Archivo de entrada  
 A continuación, se muestra el archivo bookstore.xml que se utiliza como archivo de entrada en los ejemplos incluidos en este tema:  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
