---
title: "Propiedad de eje descendiente XML Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyDescendantsAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedad de eje para elementos descendientes [Visual Baisc]"
  - "código de Visual Basic, obtener acceso a XML"
  - "XML [Visual Basic], obtener acceso"
  - "eje XML [Visual Basic], descendiente"
  - "propiedad de eje para elementos XML descendientes [Visual Basic]"
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Propiedad de eje descendiente XML Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Proporciona acceso a los descendientes de un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
## Sintaxis  
  
```  
  
object...<descendant>  
```  
  
## Elementos  
 `object`  
 Obligatorio.  Objeto <xref:System.Xml.Linq.XElement>, objeto <xref:System.Xml.Linq.XDocument>, colección de objetos <xref:System.Xml.Linq.XElement> o colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
 ...\<  
 Obligatorio.  Denota el inicio de una propiedad de eje descendiente.  
  
 `descendant`  
 Obligatorio.  Nombre de los nodos descendientes a los que se va a obtener acceso, con el formato \[`prefix``:`\]`name`.  
  
|Parte|Descripción|  
|-----------|-----------------|  
|`prefix`|Opcional.  Prefijo de espacio de nombres XML para el nodo descendiente.  Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.|  
|`name`|Obligatorio.  Nombre local del nodo descendiente.  Vea [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Obligatorio.  Denota el final de una propiedad de eje descendiente.  
  
## Valor devuelto  
 Colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## Comentarios  
 Puede usar una propiedad de eje descendiente XML para obtener acceso a los nodos descendientes por nombre de un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o bien, de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.  Use la propiedad XML `Value` para obtener acceso al valor del primer nodo descendiente en la colección devuelta.  Para obtener más información, vea [Propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte las propiedades de eje descendiente en llamadas al método <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
## Espacios de nombres XML  
 El nombre en una propiedad de eje descendiente puede usar únicamente espacios de nombres XML declarados globalmente con la instrucción `Imports`.  No puede usar espacios de nombres XML declarados localmente dentro de los literales de elemento XML.  Para obtener más información, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del objeto `contacts`.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## Ejemplo  
 En el ejemplo siguiente se declara `ns` como prefijo de espacio de nombres XML.  A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)