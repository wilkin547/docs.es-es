---
title: Literal de instrucción de procesamiento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 1906c9101f9a53bde13698d0ed17b7b8d0988c1d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981379"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literal de instrucción de procesamiento XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Elementos  
 `<?`  
 Obligatorio. Denota el inicio de la instrucción de procesamiento XML literal.  
  
 `piName`  
 Obligatorio. Asigne un nombre que indica qué aplicación los destinos de la instrucción de procesamiento. No puede empezar por "xml" o "XML".  
  
 `piData`  
 Opcional. Cadena que indica cómo la aplicación de destino de `piName` debe procesar el documento XML.  
  
 `?>`  
 Obligatorio. Denota el final de la instrucción de procesamiento.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Comentarios  
 Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML. Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento. La aplicación interpreta el significado de `piName` y `piData`.  
  
 El literal de documento XML usa la sintaxis que es similar de la instrucción de procesamiento de XML. Para obtener más información, consulte [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  El `piName` elemento no puede comenzar con las cadenas "xml" o "XML", ya que los identificadores de reserva de la especificación XML 1.0.  
  
 Puede asignar un literal de instrucción de procesamiento de XML a una variable o incluirlo en un literal de documento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea. Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.  
  
 El compilador de Visual Basic convierte el literal de instrucción de procesamiento XML en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XProcessingInstruction>
- [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
