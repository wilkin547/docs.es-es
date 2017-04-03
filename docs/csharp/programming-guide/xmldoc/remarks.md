---
title: "&lt;remarks&gt; (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remarks
- <remarks>
dev_langs:
- CSharp
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4d830e5df5af7d2c50cbf1501cbed67d1a0ffdad
ms.lasthandoff: 03/13/2017

---
# <a name="ltremarksgt-c-programming-guide"></a>&lt;remarks&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Description`  
 Descripción del miembro.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md). Esta información se muestra en la ventana Examinador de objetos.  
  
 Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
