---
title: "Literal de CDATA XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralCdata"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CDATA (literal) [Visual Basic]"
  - "CDATA (literal XML) [Visual Basic]"
  - "literales XML [Visual Basic], CDATA"
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Literal de CDATA XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es un literal que representa un objeto <xref:System.Xml.Linq.XCData>.  
  
## Sintaxis  
  
```  
<![CDATA[content]]>  
```  
  
## Elementos  
 `<![CDATA[`  
 Obligatorio.  Denota el inicio de la sección CDATA XML.  
  
 `content`  
 Obligatorio.  Contenido de texto que va a aparecer en la sección CDATA XML.  
  
 `]]>`  
 Obligatorio.  Denota el fin de la sección.  
  
## Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XCData>.  
  
## Comentarios  
 Las secciones CDATA XML contienen el texto sin formato que se debe incluir, pero no analizar, con el XML que lo contiene.  Una sección CDATA XML puede contener cualquier texto.  Esto incluye caracteres XML reservados.  La sección CDATA XML finaliza con la secuencia"\]\]\>".  Esto implica los siguientes puntos:  
  
-   No se puede usar una expresión incrustada en un literal CDATA XML porque los delimitadores de la expresión incrustada son contenido CDATA XML válido.  
  
-   Las secciones CDATA XML no pueden estar anidadas porque `content` no puede contener el valor "\]\]\>".  
  
 Se puede asignar un literal CDATA XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas pero no usa caracteres de continuación de línea.  Esto permite copiar el contenido de un documento XML y pegarlo directamente en un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte el literal CDATA XML en una llamada al constructor <xref:System.Xml.Linq.XCData.%23ctor%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea una sección CDATA que contiene el texto "Can contain literal \<XML\> tags" \(Puede contener etiquetas de literal \<XML\>\).  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-cdata-literal_1.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XCData>   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)