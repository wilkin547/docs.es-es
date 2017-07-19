---
title: "Crear nuevos atributos para elementos en DOM | Microsoft Docs"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Crear nuevos atributos para elementos en DOM
La creación de nuevos atributos es diferente de la creación de otros tipos de nodo, puesto que los atributos no son nodos, sino propiedades de un nodo de elemento y se incluyen en un **XmlAttributeCollection** asociado al elemento.  Hay varias formas de crear un atributo y adjuntarlo a un elemento:  
  
-   Para agregar un atributo a la colección de atributos de dicho elemento, obtenga el nodo de elemento y utilice **SetAttribute**.  
  
-   Cree un nodo **XmlAttribute** mediante el método **CreateAttribute**, obtenga el nodo del elemento y, a continuación, utilice el método **SetAttributeNode** para agregar el nodo a la colección de atributos de dicho elemento.  
  
 En el ejemplo siguiente se muestra cómo agregar un atributo a un elemento mediante el método **SetAttribute**.  
  
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
  
 En el ejemplo siguiente se muestra un nuevo atributo que se crea mediante el método **CreateAttribute**.  Después, se muestra el atributo agregado a la colección de atributos del elemento **book** mediante el método **SetAttributeNode**.  
  
 Dado el siguiente XML:  
  
```  
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
  
```  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 El ejemplo de código completo se puede encontrar en [XmlDocument.CreateAttribute \(Método\)](frlrfSystemXmlXmlDocumentClassCreateAttributeTopic).  
  
 También se puede crear un nodo **XmlAttribute** y utilizar los métodos **InsertBefore** o **InsertAfter** para colocarlo en la posición adecuada en la colección.  Si en la colección de atributos ya hay uno con el mismo nombre, el nodo **XmlAttribute** existente se quita de la colección y se inserta el nuevo nodo **XmlAttribute**.  Funciona del mismo modo que el método **SetAttribute**.  Estos métodos aceptan, como parámetro, un nodo existente como punto de referencia para ejecutar los métodos **InsertBefore** y **InsertAfter**.  Si no se proporciona un nodo de referencia que indique dónde insertar el nodo nuevo, con la configuración predeterminada del método **InsertAfter** el nodo nuevo se inserta al principio de la colección.  La posición predeterminada para **InsertBefore**, si no se proporciona ningún nodo de referencia, es el final de la colección.  
  
 Si creó una clase **XmlNamedNodeMap** de atributos, puede agregar un atributo por nombre mediante el [método SetNamedItem](frlrfSystemXmlXmlNamedNodeMapClassSetNamedItemTopic).  Para obtener más información, vea [Colecciones de nodos en NamedNodeMaps y NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## Atributos predeterminados  
 Si creó un elemento declarado para tener un atributo predeterminado, el Modelo de objetos de documento \(DOM\) crea un nuevo atributo predeterminado con su valor predeterminado y lo adjunta al elemento.  Los nodos secundarios del atributo predeterminado se crean también en este momento.  
  
## Nodos secundarios de atributo  
 El valor de un nodo de atributo se convierte en sus nodos secundarios.  Hay solo dos tipos válidos de nodos secundarios: los nodos **XmlText** y **XmlEntityReference**.  Se trata de nodos secundarios en el sentido de que métodos como **FirstChild** y **LastChild** los procesan como tales.  Esta distinción de un atributo con nodos secundarios es importante cuando se intenta quitar atributos o nodos secundarios de atributo.  Para obtener más información, vea [Cómo quitar atributos de un nodo de elemento en DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)