---
title: "Literal de instrucci&#243;n de procesamiento XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralProcessingInstruction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal de instrucción de procesamiento [Visual Basic]"
  - "literales XML [Visual Basic], instrucción de procesamiento"
  - "literal de instrucción de procesamiento XML [Visual Basic]"
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Literal de instrucci&#243;n de procesamiento XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es un literal que representa un objeto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## Sintaxis  
  
```  
<?piName [ = piData ] ?>  
```  
  
## Elementos  
 `<?`  
 Obligatorio.  Denota el inicio del literal de instrucción de procesamiento XML.  
  
 `piName`  
 Obligatorio.  Nombre que indica la aplicación a la que va destinada la instrucción de procesamiento.  No puede comenzar con "xml" ni "XML".  
  
 `piData`  
 Opcional.  Cadena que indica cómo la aplicación especificada por `piName` debe procesar el documento XML.  
  
 `?>`  
 Obligatorio.  Denota el fin de la instrucción de procesamiento.  
  
## Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## Comentarios  
 Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML.  Cuando una aplicación carga un documento XML, puede comprobar las instrucciones de procesamiento XML para determinar cómo debe procesar el documento.  La aplicación interpreta el significado de `piName` y `piData`.  
  
 El literal de documento XML usa una sintaxis similar a la de la instrucción de procesamiento XML.  Para obtener más información, vea [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  El elemento `piName` no puede comenzar con las cadenas "xml" ni "XML" porque la especificación de XML 1.0 se reserva esos identificadores.  
  
 Puede asignar un literal de instrucción de procesamiento XML a una variable, o bien, incluirlo en un literal de documento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.  Esto permite copiar el contenido de un documento XML y pegarlo directamente en un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte el literal de instrucción de procesamiento XML en una llamada al constructor <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-processing-instructi_1.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XProcessingInstruction>   
 [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)