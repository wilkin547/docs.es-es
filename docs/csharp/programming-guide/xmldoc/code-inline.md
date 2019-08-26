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
ms.openlocfilehash: c881b9ec577fb04381f9e10c7df8f9d0da44cd66
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588183"
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
 La etiqueta \<c> le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código. Use [\<code>](./code.md) para indicar varias líneas como código.  
  
 Compile con [/doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
