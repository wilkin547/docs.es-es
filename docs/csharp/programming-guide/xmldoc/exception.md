---
title: '&lt;exception&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: c865fe97db16c95396e03747958d3590e80de614
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259693"
---
# <a name="ltexceptiongt-c-programming-guide"></a>&lt;exception&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parámetros  
 cref = "`member`"  
 Una referencia a una excepción que está disponible desde el entorno de compilación actual. El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML. `member` debe aparecer entre comillas dobles (" ").  
  
 Para más información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Descripción de la excepción.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<exception> le permite especificar qué excepciones se pueden producir. Esta etiqueta se puede aplicar a definiciones de métodos, propiedades, eventos e indizadores.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
 Para más información sobre el control de excepciones, vea [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
