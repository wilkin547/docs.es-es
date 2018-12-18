---
title: '&lt;c&gt;: Guía de programación de C#'
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
ms.openlocfilehash: 5ebdb275ffa9b735d0d68b3d9b4685880a849a7a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236419"
---
# <a name="ltcgt-c-programming-guide"></a>&lt;c&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `text`  
 El texto que le gustaría indicar como código.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<c> le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código. Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) para indicar varias líneas como código.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
