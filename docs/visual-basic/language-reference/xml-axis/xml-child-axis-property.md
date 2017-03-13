---
title: "Propiedades de eje secundario XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyChildAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedad de eje para elementos secundarios [Visual Basic]"
  - "código de Visual Basic, obtener acceso a XML"
  - "XML [Visual Basic], obtener acceso"
  - "eje XML [Visual Basic], secundarios"
  - "propiedad de eje para elementos XML secundarios [Visual Basic]"
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Propiedades de eje secundario XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
## Sintaxis  
  
```  
  
object.<child>  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`object`|Requerido.  Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.|  
|.\<|Requerido.  Denota el inicio de una propiedad de eje secundario.|  
|`child`|Requerido.  Nombre de los nodos secundarios para obtener acceso, con el formato \[`prefix``:`\]`name`.<br /><br /> -   `Prefix` \(opcional\).  Prefijo de espacio de nombres XML para el nodo secundario.  Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.<br />-   `Name` \(requerido\).  Nombre del nodo secundario local.  Vea [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|\>|Requerido.  Denota el final de una propiedad de eje secundario.|  
  
## Valor devuelto  
 Una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## Comentarios  
 Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.  Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta.  Para obtener más información, vea [Propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte las propiedades de eje secundario en llamadas al método <xref:System.Xml.Linq.XContainer.Elements%2A>.  
  
## Espacios de nombres XML  
 El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`.  No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.  Para obtener más información, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.  A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Patrick Hines`  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)