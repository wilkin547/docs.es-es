---
title: "Literal de comentario XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal de comentario [Visual Basic]"
  - "literal de comentario XML [Visual Basic]"
  - "comentarios XML, agregar [Visual Basic]"
  - "literales XML [Visual Basic], comentario"
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Literal de comentario XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es un literal que representa un objeto <xref:System.Xml.Linq.XComment>.  
  
## Sintaxis  
  
```  
<!-- content -->  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`<!--`|Obligatorio.  Denota el inicio del comentario XML.|  
|`content`|Obligatorio.  Texto que va a aparecer en el comentario XML.  No puede contener ninguna serie de dos guiones \(\-\-\) ni finalizar con un guión adyacente a la etiqueta de cierre.|  
|`-->`|Obligatorio.  Denota el final del comentario XML.|  
  
## Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XComment>.  
  
## Comentarios  
 Los literales de comentario XML no incluyen el contenido del documento; contienen información sobre el documento.  La sección de comentario XML finaliza con la secuencia"\-\-\>".  Esto implica los siguientes puntos:  
  
-   No se puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.  
  
-   Las secciones de comentario XML no pueden estar anidadas porque `content` no puede contener el valor "\-\-\>".  
  
 Puede asignar un literal de comentario XML a una variable, o bien, puede incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.  Esta característica permite copiar el contenido de un documento XML y pegarlo directamente en un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte el literal de comentario XML en una llamada al constructor <xref:System.Xml.Linq.XComment.%23ctor%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un comentario XML que contiene el texto "This is a comment".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XComment>   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)