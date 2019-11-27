---
title: Literal de CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349431"
---
# <a name="xml-cdata-literal-visual-basic"></a>Literal de CDATA XML (Visual Basic)
Literal que representa un objeto <xref:System.Xml.Linq.XCData>.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Elementos  
 `<![CDATA[`  
 Obligatorio. Denota el inicio de la sección XML CDATA.  
  
 `content`  
 Obligatorio. Contenido de texto para que aparezca en la sección XML CDATA.  
  
 `]]>`  
 Obligatorio. Denota el final de la sección.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Comentarios  
 Las secciones CDATA XML contienen texto sin formato que se debe incluir, pero no analizar, con el XML que lo contiene. Una sección CDATA XML puede contener cualquier texto. Esto incluye los caracteres XML reservados. La sección CDATA XML finaliza con la secuencia "]] >". Esto implica los puntos siguientes:  
  
- No se puede usar una expresión insertada en un literal CDATA XML porque los delimitadores de expresión incrustados son contenido XML CDATA válido.  
  
- Las secciones CDATA XML no se pueden anidar porque `content` no pueden contener el valor "]] >".  
  
 Puede asignar un literal CDATA XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
> Un literal XML puede abarcar varias líneas, pero no utiliza caracteres de continuación de línea. Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.  
  
 El compilador Visual Basic convierte el literal CDATA XML en una llamada al constructor <xref:System.Xml.Linq.XCData.%23ctor%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener etiquetas de > XML de \<literal".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XCData>
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
