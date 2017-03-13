---
title: "Value (Propiedad XML) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyExtensionValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Value (propiedad) [Visual Basic]"
  - "código de Visual Basic, obtener acceso a XML"
  - "eje XML [Visual Basic], Value"
  - "Value (propiedad XML) [Visual Basic]"
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Value (Propiedad XML) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Proporciona acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## Sintaxis  
  
```  
  
object.Value  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`object`|Obligatorio.  Colección de objetos <xref:System.Xml.Linq.XElement>.|  
  
## Valor devuelto  
 `String` que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía.  
  
## Comentarios  
 La propiedad <xref:System.Xml.Linq.XElement.Value%2A> facilita el acceso al valor del primer elemento en una colección de objetos <xref:System.Xml.Linq.XElement>.  Esta propiedad comprueba primero si la colección contiene por lo menos un objeto.  Si la colección está vacía, esta propiedad devuelve `Nothing`.  De lo contrario, devuelve el valor de la propiedad <xref:System.Xml.Linq.XElement.Value%2A> del primer elemento de la colección.  
  
> [!NOTE]
>  Al obtener acceso al valor de un atributo XML mediante el identificador '@', el valor del atributo se devuelve como `String` y no se necesita especificar explícitamente la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.  
  
 Para obtener acceso a los otros elementos de una colección, puede usar la propiedad de los indizadores en las extensiones XML.  Para obtener más información, vea [Propiedad de indizador de extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).  
  
## Herencia  
 La mayoría de los usuarios no tendrán que implementar <xref:System.Collections.Generic.IEnumerable%601> y, por consiguiente, podrán omitir esta sección.  
  
 La propiedad <xref:System.Xml.Linq.XElement.Value%2A> es una propiedad de extensión de los tipos que implementan `IEnumerable(Of XElement)`.  El enlace de esta propiedad de extensión es como el enlace de los métodos de extensión: si un tipo implementa una de las interfaces y define una propiedad denominada "Value", esa propiedad tiene prioridad sobre la propiedad de extensión.  En otras palabras, esta propiedad <xref:System.Xml.Linq.XElement.Value%2A> se puede invalidar definiendo una nueva propiedad en una clase que implemente `IEnumerable(Of XElement)`.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para obtener acceso al primer nodo en una colección de objetos <xref:System.Xml.Linq.XElement>.  En el ejemplo se usa la propiedad de eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que se encuentran en el objeto `contact`.  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `Phone number: 206-555-0144`  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de objetos <xref:System.Xml.Linq.XAttribute>.  En el ejemplo se usa la propiedad de eje de atributo para mostrar el valor del atributo `type` de todos los elementos `phone`.  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 Este código muestra el texto siguiente:  
  
 `home`  
  
 `work`  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [métodos de extensión.](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Propiedad de indizador de extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)   
 [Propiedades de eje secundario XML](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [Propiedad Axis para atributo XML](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)