---
title: "Literal de documento XML (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralDocument"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal de documento [Visual Basic]"
  - "literal de documento XML [Visual Basic]"
  - "documentos XML [Visual Basic], crear"
  - "literales XML [Visual Basic], documento"
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Literal de documento XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es un literal que representa un objeto <xref:System.Xml.Linq.XDocument>.  
  
## Sintaxis  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`encoding`|Opcional.  Texto literal que declara la codificación que el documento usa.|  
|`standalone`|Opcional.  Texto literal.  Debe ser "sí" o "no".|  
|`piCommentList`|Opcional.  Lista de instrucciones de procesamiento XML y comentarios XML.  Tiene el siguiente formato:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Cada `piComment` ``  puede ser uno de los siguientes:<br /><br /> -   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Obligatorio.  Elemento raíz del documento.  Tiene uno de los siguientes formatos:<br /><br /> <ul><li>[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Expresión incrustada con el formato `<%=` `elementExp` `%>`.  `elementExp` devuelve uno de los siguientes elementos:<br /><br /> <ul><li>Un objeto <xref:System.Xml.Linq.XElement>.</li><li>Una colección que contiene un objeto <xref:System.Xml.Linq.XElement> y cualquier número de objetos <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment>.</li></ul></li></ul><br /> Para obtener más información, vea [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XDocument>.  
  
## Comentarios  
 La declaración XML identifica un literal de documento XML en el inicio del literal.  Aunque cada literal de documento XML debe tener exactamente un elemento XML raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.  
  
 Un literal de documento XML no puede aparecer en un elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.  Esto permite copiar el contenido de un documento XML y pegarlo directamente en un programa de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] convierte el literal de documento XML en llamadas a los constructores de <xref:System.Xml.Linq.XDocument.%23ctor%2A> y <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un documento XML que tiene una declaración, una instrucción de procesamiento, un comentario y un elemento XML que contiene otro elemento.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-document-literal_1.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument>   
 [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)