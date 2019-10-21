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
ms.openlocfilehash: 9454ef8cc4b72d1d6bdcac26faf76eb17080328c
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523535"
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
  
 Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
