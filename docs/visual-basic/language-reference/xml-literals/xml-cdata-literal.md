---
title: Literal de CDATA XML (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 24e52bf203ff3df57e26137da24abcc2cb7e8e20
ms.lasthandoff: 03/13/2017

---
# <a name="xml-cdata-literal-visual-basic"></a>Literal de CDATA XML (Visual Basic)
Un literal que representa un <xref:System.Xml.Linq.XCData>objeto.</xref:System.Xml.Linq.XCData>  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Elementos  
 `<![CDATA[`  
 Obligatorio. Denota el inicio de la sección CDATA XML.  
  
 `content`  
 Obligatorio. Contenido de texto que aparezca en la sección CDATA XML.  
  
 `]]>`  
 Obligatorio. Denota el final de la sección.  
  
## <a name="return-value"></a>Valor devuelto  
 Un <xref:System.Xml.Linq.XCData>objeto.</xref:System.Xml.Linq.XCData>  
  
## <a name="remarks"></a>Comentarios  
 Las secciones CDATA XML contienen texto sin formato que debe incluir, pero no analizar, con el XML que lo contiene. Una sección CDATA XML puede contener cualquier texto. Esto incluye los caracteres XML reservados. La sección CDATA XML finaliza con la secuencia "]] >". Esto implica los siguientes puntos:  
  
-   No puede usar una expresión incrustada en un literal de CDATA XML porque los delimitadores de expresión incrustada son contenido CDATA XML válido.  
  
-   No se pueden anidar las secciones CDATA XML porque `content` no puede contener el valor "]] >".  
  
 Puede asignar un literal de CDATA XML a una variable o incluirlo en un literal de elemento XML.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas pero no usa caracteres de continuación de línea. Esto le permite copiar el contenido de un documento XML y péguelo directamente en un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programa.  
  
 El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador convierte el literal de CDATA XML a una llamada a la <xref:System.Xml.Linq.XCData.%23ctor%2A>constructor.</xref:System.Xml.Linq.XCData.%23ctor%2A>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener literales \<XML > etiquetas".  
  
 [!code-vb[23 de VbXMLSamples #](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData>   
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
