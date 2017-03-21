---
title: "(Visual Basic) del Literal de instrucción de procesamiento XML | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 2903297fa22cd8dc10bc4b12abaa754d4f6284f2
ms.lasthandoff: 03/13/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literal de instrucción de procesamiento XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XProcessingInstruction>objeto.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Elementos  
 `<?`  
 Obligatorio. Denota el inicio de la instrucción de procesamiento XML literal.  
  
 `piName`  
 Obligatorio. El nombre que indica qué aplicación los destinos de instrucción de procesamiento. No puede comenzar con "xml" o "XML".  
  
 `piData`  
 Opcional. Cadena que indica cómo la aplicación de destino de `piName` debe procesar el documento XML.  
  
 `?>`  
 Obligatorio. Denota el final de la instrucción de procesamiento.  
  
## <a name="return-value"></a>Valor devuelto  
 Un <xref:System.Xml.Linq.XProcessingInstruction>objeto.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="remarks"></a>Comentarios  
 Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML. Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento. La aplicación interpreta el significado de `piName` y `piData`.  
  
 El literal de documento XML utiliza sintaxis similar a la de la instrucción de procesamiento de XML. Para obtener más información, consulte [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  El `piName` elemento no puede comenzar con las cadenas "xml" o "XML" porque la especificación XML 1.0 reserva esos identificadores.  
  
 Puede asignar un literal de instrucción de procesamiento XML a una variable o incluirlo en un literal de documento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea. Esto le permite copiar el contenido de un documento XML y péguelo directamente en un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte el literal de instrucción de procesamiento XML en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>constructor.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.  
  
 [!code-vb[VbXMLSamples&#28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
