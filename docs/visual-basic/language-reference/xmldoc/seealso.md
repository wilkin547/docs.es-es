---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 5999a4ebcc90f21ee8331b96ffb2a50f7905b1b6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411517"
---
# <a name="seealso-visual-basic"></a>\<seealso> (Visual Basic)
Especifica un vínculo que aparece en la sección Vea también.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML. `member` debe aparecer entre comillas dobles (" ").  
  
## <a name="remarks"></a>Observaciones  
 Use la `<seealso>` etiqueta para especificar el texto que desea que aparezca en la sección Vea también. [\<see>](see.md)Se usa para especificar un vínculo desde dentro del texto.  
  
 Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<seealso>` etiqueta de la `DoesRecordExist` sección Comentarios para hacer referencia al `UpdateRecord` método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
