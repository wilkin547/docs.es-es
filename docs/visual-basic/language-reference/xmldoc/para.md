---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352303"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
Especifica que el contenido está formateado como un párrafo.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parámetros  
 `content`  
 El texto del párrafo.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta `<para>` es para su uso dentro de una etiqueta, como [\<> de Resumen](../../../visual-basic/language-reference/xmldoc/summary.md), [\<comentarios >](../../../visual-basic/language-reference/xmldoc/remarks.md)o [\<devuelve >](../../../visual-basic/language-reference/xmldoc/returns.md)y permite agregar la estructura al texto.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<para>` para dividir la sección Comentarios para el método `UpdateRecord` en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
