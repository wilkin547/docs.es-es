---
title: Literal de documento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 09ab9d0bf3feeea70ddbc094183406a6fd646c1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690519"
---
# <a name="xml-document-literal-visual-basic"></a>Literal de documento XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XDocument> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`encoding`|Opcional. Se utiliza el texto literal que declara la codificación que el documento.|  
|`standalone`|Opcional. Texto literal. Debe ser "yes" o "no".|  
|`piCommentList`|Opcional. Lista de instrucciones de procesamiento XML y los comentarios XML. Tiene el formato siguiente:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Cada `piComment` puede ser uno de los siguientes:<br /><br /> -   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Obligatorio. Elemento raíz del documento. El formato es uno de los siguientes:<br /><br /> <ul><li>[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>La forma expresión incrustada `<%=` `elementExp` `%>`. El `elementExp` devuelve uno de los siguientes:<br /><br /> <ul><li>Un objeto <xref:System.Xml.Linq.XElement>.</li><li>Una colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment> objetos.</li></ul></li></ul><br /> Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Comentarios  
 Un literal de documento XML se identifica mediante la declaración XML al principio del literal. Aunque cada literal de documento XML debe tener exactamente un elemento XML de raíz, puede tener cualquier número de instrucciones de procesamiento XML y los comentarios XML.  
  
 Un literal de documento XML no puede aparecer en un elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.  
  
 El compilador de Visual Basic convierte el literal de documento XML en llamadas a la <xref:System.Xml.Linq.XDocument.%23ctor%2A> y <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
