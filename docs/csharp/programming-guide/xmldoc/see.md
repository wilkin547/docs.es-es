---
title: "&lt;see&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- CSharp
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 831caae9574c25f16e8b2ede734746f48019198e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltseegt-c-programming-guide"></a>&lt;see&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parámetros  
 cref = "`member`"  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML. Coloque *member* entre comillas dobles (" ").  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<see> permite especificar un vínculo desde el texto. Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) para indicar que el texto debe colocarse en una sección Vea también. Use el [atributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código.  
  
 Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
 En el ejemplo siguiente, se muestra una etiqueta \<see> dentro de una sección de resumen.  
  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

