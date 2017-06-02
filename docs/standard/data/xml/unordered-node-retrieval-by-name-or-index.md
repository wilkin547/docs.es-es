---
title: "Recuperaci&#243;n de nodos desordenados por nombre o &#237;ndice | Microsoft Docs"
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Recuperaci&#243;n de nodos desordenados por nombre o &#237;ndice
**XmlNamedNodeMap** se describe en la especificación del W3C como NamedNodeMap y es necesario para controlar un conjunto de nodos desordenado con la capacidad de hacer referencia a los mismos mediante su nombre o índice.  El único modo de tener acceso a un **XmlNamedNodeMap** es devolverlo a través de un método o propiedad.  Hay tres métodos o propiedades que devuelven un **XmlNamedNodeMap**:  
  
-   XmlElement.Attributes  
  
-   XmlDocumentType.Entities  
  
-   XmlDocumentType.Notations  
  
 Por ejemplo, la propiedad **XmlDocumentType.Entities** obtiene la colección de nodos **XmlEntity** declarada en la declaración de tipos de documento.  Esta colección se devuelve como **XmlNamedNodeMap** y se puede recorrer en iteración mediante la propiedad **Count**. También se puede mostrar información de entidad.  Para obtener un ejemplo de cómo recorrer en iteración un **XmlNamedNodeMap**, vea [XmlDocumentType.Entities \(Propiedad\)](frlrfSystemXmlXmlDocumentTypeClassEntitiesTopic).  
  
 **XmlAttributeCollection** se deriva de **XmlNamedNodeMap** y solo los atributos son modificables, mientras que las notaciones y entidades son de solo lectura.  Si utiliza **XmlNamedNodeMap** para los atributos, puede obtener nodos para dichos atributos en función de sus nombres XML.  De este modo se proporciona un método sencillo de manipular la colección de atributos en un nodo de elemento.  Esto se puede contrastar directamente con **XmlNodeList**, que también implementa la interfaz **IEnumerable**, pero con un descriptor de acceso de índice en lugar de una cadena.  Los métodos **RemoveNamedItem** y **SetNamedItem** solo se utilizan con respecto a **XmlAttributeCollection**.  Si se agrega o quita de una colección de atributos, independientemente de que se utilice la implementación **AttributeCollection** o **XmlNamedNodeMap**, se modifica la colección de atributos del elemento.  En el ejemplo de código siguiente se muestra cómo se mueve un atributo y se crea un atributo nuevo.  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 Para ver un ejemplo de código adicional donde se muestre un atributo que se ha quitado de un **AttributeCollection**, vea [XmlNamedNodeMap.RemoveNamedItem \(Método\)](frlrfSystemXmlXmlNamedNodeMapClassRemoveNamedItemTopic).  Para obtener más información sobre los métodos y propiedades, vea [XmlNamedNodeMap Members](frlrfSystemXmlXmlNamedNodeMapMembersTopic).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)