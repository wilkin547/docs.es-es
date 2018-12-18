---
title: '&lt;seealso&gt;: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: eec4a0c2041d7d10b5887950bfec03ec8847c82b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244796"
---
# <a name="ltseealsogt-c-programming-guide"></a>&lt;seealso&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 cref = "`member`"  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member` debe aparecer entre comillas dobles (" ").  
  
 Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<seealso> le permite especificar el texto que quiere que aparezca en una sección Vea también. Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) para especificar un vínculo desde dentro del texto.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Vea [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para obtener un ejemplo del uso de \<seealso>.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
