---
title: Crear nuevos atributos para elementos en DOM
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Crear nuevos atributos para elementos en DOM
Creación de nuevos atributos es diferente de la creación de otros tipos de nodo, porque los atributos no son nodos, pero son propiedades de un nodo de elemento y están incluidos en un **XmlAttributeCollection** asociada al elemento. Hay varias formas de crear un atributo y adjuntarlo a un elemento:  
  
-   Obtenga el nodo de elemento y utilice **SetAttribute** para agregar un atributo a la colección de atributos de ese elemento.  
  
-   Crear un **XmlAttribute** nodo mediante el **CreateAttribute** método, obtenga el nodo de elemento y luego use **SetAttributeNode** para agregar el nodo a la colección de atributos de ese elemento.  
  
 En el ejemplo siguiente se muestra cómo agregar un atributo a un elemento mediante la **SetAttribute** método.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 En el ejemplo siguiente se muestra un nuevo atributo que se crea mediante la **CreateAttribute** método. A continuación, muestra el atributo agregado a la colección de atributos de la **libreta de** elemento utilizando el **SetAttributeNode** método.  
  
 Dado el siguiente XML:  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 cree un atributo nuevo y asígnele un valor:  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 y asócielo al elemento:  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 **Salida**  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 El ejemplo de código completo se puede encontrar en <xref:System.Xml.XmlDocument.CreateAttribute%2A>.  
  
 También puede crear un **XmlAttribute** nodo y use la **InsertBefore** o **InsertAfter** métodos para colocarlo en la posición adecuada en la colección. Si un atributo con el mismo nombre ya está presente en la colección de atributos existente **XmlAttribute** nodo se quita de la colección y la nueva **XmlAttribute** se inserta el nodo. Esta opción realiza la misma manera que el **SetAttribute** método. Estos métodos aceptan, como parámetro, un nodo existente como punto de referencia para realizar la **InsertBefore** y **InsertAfter**. Si no proporciona un nodo de referencia que indique dónde insertar el nuevo nodo, el valor predeterminado para la **InsertAfter** método consiste en Insertar el nuevo nodo al principio de la colección. La posición predeterminada para la **InsertBefore**, si no se proporciona ningún nodo de referencia, es el final de la colección.  
  
 Si ha creado un **XmlNamedNodeMap** de atributos, puede agregar un atributo por nombre mediante el <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Para obtener más información, consulte [colecciones de nodos en NamedNodeMaps y NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## <a name="default-attributes"></a>Atributos predeterminados  
 Si creó un elemento declarado para tener un atributo predeterminado, el Modelo de objetos de documento (DOM) crea un nuevo atributo predeterminado con su valor predeterminado y lo adjunta al elemento. Los nodos secundarios del atributo predeterminado se crean también en este momento.  
  
## <a name="attribute-child-nodes"></a>Nodos secundarios de atributo  
 El valor de un nodo de atributo se convierte en sus nodos secundarios. Hay solo dos tipos de nodos secundarios válidos: **XmlText** nodos, y **XmlEntityReference** nodos. Estos son los nodos secundarios en el sentido de que métodos como **FirstChild** y **LastChild** procesarlos como nodos secundarios. Esta distinción de un atributo con nodos secundarios es importante cuando se intenta quitar atributos o nodos secundarios de atributo. Para obtener más información, consulte [cómo quitar atributos de un nodo de elemento en DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
