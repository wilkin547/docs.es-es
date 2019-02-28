---
title: Literal de CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981249"
---
# <a name="xml-cdata-literal-visual-basic"></a>Literal de CDATA XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XCData> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Elementos  
 `<![CDATA[`  
 Obligatorio. Denota el inicio de la sección XML CDATA.  
  
 `content`  
 Obligatorio. Contenido de texto que aparezca en la sección XML CDATA.  
  
 `]]>`  
 Obligatorio. Denota el final de la sección.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Comentarios  
 Secciones de CDATA XML contienen texto sin formato que debe incluir, pero no puede analizar, con el XML que lo contiene. Una sección CDATA XML puede contener cualquier texto. Esto incluye los caracteres XML reservados. La sección CDATA XML finaliza con la secuencia "]] >". Esto implica los siguientes puntos:  
  
-   No se puede usar una expresión incrustada en un literal de CDATA XML porque los delimitadores de expresión incrustada son contenido de CDATA XML válido.  
  
-   No se puede anidar las secciones de CDATA XML porque `content` no puede contener el valor "]] >".  
  
 Puede asignar un literal de CDATA XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas, pero no usa caracteres de continuación de línea. Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.  
  
 El compilador de Visual Basic convierte el literal de CDATA XML a una llamada a la <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener literal \<XML > etiquetas".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XCData>
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
