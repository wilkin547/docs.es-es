---
title: '<paramref>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 9612fb61151953e0d3b70a4803aafeb571aec7dd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477949"
---
# <a name="paramref-c-programming-guide"></a>\<paramref> (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 Nombre del parámetro al que se hace referencia. Ponga el nombre entre comillas dobles (" ").  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<paramref> ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque \<summary> o \<comments>) hace referencia a un parámetro. El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
