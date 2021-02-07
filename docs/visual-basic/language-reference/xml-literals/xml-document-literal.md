---
description: 'Más información acerca de: literal de documento XML (Visual Basic)'
title: Literal de documento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: d268f205c9357598a631216879b424dd8155268a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700317"
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`encoding`|Opcional. Texto literal que declara Qué codificación utiliza el documento.|  
|`standalone`|Opcional. Texto literal. Debe ser "Yes" o "no".|  
|`piCommentList`|Opcional. Lista de instrucciones de procesamiento XML y comentarios XML. Tiene el siguiente formato:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Cada `piComment` puede ser uno de los siguientes:<br /><br /> -   [Literal de instrucción de procesamiento XML](xml-processing-instruction-literal.md).<br />-   [Literal de comentario XML](xml-comment-literal.md).|  
|`rootElement`|Necesario. Elemento raíz del documento. El formato es uno de los siguientes:<br /><br /> <ul><li>[Literal de elemento XML](xml-element-literal.md).</li><li>Expresión insertada con el formato `<%=` `elementExp` `%>` . `elementExp`Devuelve uno de los siguientes:<br /><br /> <ul><li>Objeto <xref:System.Xml.Linq.XElement>.</li><li>Colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> objetos y <xref:System.Xml.Linq.XComment> .</li></ul></li></ul><br /> Para obtener más información, vea [expresiones incrustadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Valor devuelto  

 Objeto <xref:System.Xml.Linq.XDocument>.  
  
## <a name="remarks"></a>Observaciones  

 Un literal de documento XML se identifica mediante la declaración XML al principio del literal. Aunque cada literal de documento XML debe tener exactamente un elemento XML raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.  
  
 Un literal de documento XML no puede aparecer en un elemento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea. Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.  
  
 El compilador Visual Basic convierte el literal del documento XML en llamadas a los <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructores y.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [Literal de instrucción de procesamiento XML](xml-processing-instruction-literal.md)
- [Literal de comentario XML](xml-comment-literal.md)
- [Literal de elemento XML](xml-element-literal.md)
- [Literales XML](index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Expresiones insertadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
