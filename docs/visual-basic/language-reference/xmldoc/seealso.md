---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: ca0b298c0c95e018febbcfac95de7db05bffedb8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287890"
---
# <a name="seealso-visual-basic"></a>\<seealso > (Visual Basic)
Especifica un vínculo que aparece en la sección Vea también.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML. `member` debe aparecer entre comillas dobles (" ").  
  
## <a name="remarks"></a>Comentarios  
 Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en una sección Vea también. Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) para especificar un vínculo desde dentro del texto.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<seealso>` etiquetar en el `DoesRecordExist` comentarios la sección para hacer referencia a la `UpdateRecord` método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
