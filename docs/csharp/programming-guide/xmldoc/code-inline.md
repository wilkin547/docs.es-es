---
title: '<c>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: f97e8a8f07b13e509516d13cb5181109f2340e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474194"
---
# <a name="c-c-programming-guide"></a>\<c> (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a>Parámetros  
 `text`  
 El texto que le gustaría indicar como código.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<c> le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código. Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) para indicar varias líneas como código.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
