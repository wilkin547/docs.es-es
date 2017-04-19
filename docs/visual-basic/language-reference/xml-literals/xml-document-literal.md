---
title: Literal de documento XML (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5d64faddad66eba4029969654388ba7df17e5854
ms.lasthandoff: 03/13/2017

---
# <a name="xml-document-literal-visual-basic"></a>Literal de documento XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XDocument>objeto.</xref:System.Xml.Linq.XDocument>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`encoding`|Opcional. Texto literal que declara la codificación que el documento utiliza.|  
|`standalone`|Opcional. Texto literal. Debe ser "Sí" o "no".|  
|`piCommentList`|Opcional. Lista de instrucciones de procesamiento XML y comentarios XML. Tiene el formato siguiente:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Cada `piComment`puede ser uno de los siguientes:<br /><br /> -   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Obligatorio. Elemento raíz del documento. El formato es uno de los siguientes:<br /><br /> <ul><li>[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Expresión del formulario incrustada `<%=` `elementExp` `%>`. El `elementExp` devuelve uno de los siguientes:<br /><br /> <ul><li>Un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement></li><li>Una colección que contiene un <xref:System.Xml.Linq.XElement>objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction>y <xref:System.Xml.Linq.XComment>objetos.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></li></ul></li></ul><br /> Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valor devuelto  
 Un <xref:System.Xml.Linq.XDocument>objeto.</xref:System.Xml.Linq.XDocument>  
  
## <a name="remarks"></a>Comentarios  
 Un literal de documento XML se identifica mediante la declaración XML en el inicio del literal. Aunque cada literal de documento XML debe tener exactamente un elemento XML de raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.  
  
 Un literal de documento XML no puede aparecer en un elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esto le permite copiar el contenido de un documento XML y péguelo directamente en un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte el literal de documento XML en llamadas a la <xref:System.Xml.Linq.XDocument.%23ctor%2A>y <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>constructores.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
 [!code-vb[VbXMLSamples Nº&30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>   
 [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
