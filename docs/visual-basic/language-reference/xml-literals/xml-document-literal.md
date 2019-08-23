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
ms.openlocfilehash: 8a489be46295c213b7a8b355eb3c9786d49dd8f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958499"
---
# <a name="xml-document-literal-visual-basic"></a>Literal de documento XML (Visual Basic)
Literal que representa un <xref:System.Xml.Linq.XDocument> objeto.  
  
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
|`encoding`|Opcional. Texto literal que declara Qué codificación utiliza el documento.|  
|`standalone`|Opcional. Texto literal. Debe ser "Yes" o "no".|  
|`piCommentList`|Opcional. Lista de instrucciones de procesamiento XML y comentarios XML. Tiene el siguiente formato:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Cada `piComment` puede ser uno de los siguientes:<br /><br /> -   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Necesario. Elemento raíz del documento. El formato es uno de los siguientes:<br /><br /> <ul><li>[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Expresión insertada con el `<%=` formato `elementExp` `%>`. `elementExp` Devuelve uno de los siguientes:<br /><br /> <ul><li>Un objeto <xref:System.Xml.Linq.XElement>.</li><li>Colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> objetos y <xref:System.Xml.Linq.XComment> .</li></ul></li></ul><br /> Para obtener más información, vea [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Comentarios  
 Un literal de documento XML se identifica mediante la declaración XML al principio del literal. Aunque cada literal de documento XML debe tener exactamente un elemento XML raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.  
  
 Un literal de documento XML no puede aparecer en un elemento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.  
  
 El compilador Visual Basic convierte el literal del documento XML en llamadas <xref:System.Xml.Linq.XDocument.%23ctor%2A> a <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> los constructores y.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
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
