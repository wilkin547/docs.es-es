---
title: "Propiedad de indizador de extensi&#243;n (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionIndexer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "indizador de extensión [Visual Basic]"
  - "código de Visual Basic, obtener acceso a XML"
  - "XML [Visual Basic], obtener acceso"
  - "indizador de extensión XML [Visual Basic]"
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Propiedad de indizador de extensi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona acceso a los elementos individuales de una colección.  
  
## Sintaxis  
  
```  
  
object(index)  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`object`|Obligatorio.  Colección que se puede consultar.  Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.|  
|\(|Obligatorio.  Denota el inicio de la propiedad de indizador.|  
|`index`|Obligatorio.  Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.|  
|\)|Obligatorio.  Denota el fin de la propiedad de indizador.|  
  
## Valor devuelto  
 Objeto de la ubicación especificada en la colección, o bien, `Nothing` si el índice está fuera del intervalo.  
  
## Comentarios  
 Puede usar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección.  Esta propiedad de indizador se usa normalmente en el resultado de las propiedades de eje XML.  Las propiedades de eje secundario XML y descendiente XML devuelven colecciones de objetos <xref:System.Xml.Linq.XElement> o un valor de atributo.  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte propiedades de indizador de extensión en las llamadas al método `ElementAtOrDefault`. A diferencia de un indizador de matriz, el método `ElementAtOrDefault` devuelve `Nothing` si el índice está fuera del intervalo.  Este comportamiento es útil cuando no se puede determinar con facilidad el número de elementos en una colección.  
  
 Esta propiedad de indizador es similar a una propiedad de extensión de las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: se usa únicamente si la colección no tiene indizador o una propiedad predeterminada.  
  
 Para obtener acceso al valor del primer elemento en una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, puede usar la propiedad XML `Value`.  Para obtener más información, vea [Propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el indizador de extensión para obtener acceso al segundo nodo secundario en una colección de objetos <xref:System.Xml.Linq.XElement>.  Se obtiene acceso a la colección mediante la propiedad de eje secundario, que obtiene todos los elementos secundarios denominados `phone` del objeto `contact`.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/extension-indexer-property_1.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Second phone number: 425-555-0145`  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)