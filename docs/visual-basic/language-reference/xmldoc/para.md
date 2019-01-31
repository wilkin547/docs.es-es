---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: de0387298f6ff505b286db35047065ef88541a62
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280454"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
Especifica que el contenido se da formato como un párrafo.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `content`  
 El texto del párrafo.  
  
## <a name="remarks"></a>Comentarios  
 El `<para>` etiqueta es para su uso dentro de una etiqueta, como [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<devuelve >](../../../visual-basic/language-reference/xmldoc/returns.md), y le permite agregar estructura al texto.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<para>` etiqueta para dividir la sección Comentarios para el `UpdateRecord` método en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
