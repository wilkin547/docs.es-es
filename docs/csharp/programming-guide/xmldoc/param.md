---
title: '&lt;param&gt;: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: fca53a3cd5490c28c8fabcf69446fe4a55d60b4e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236965"
---
# <a name="ltparamgt-c-programming-guide"></a>&lt;param&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `name`  
 Nombre de un parámetro de método. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Descripción del parámetro.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<param> debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método. Para documentar varios parámetros, use varias etiquetas \<param>.  
  
 El texto de la etiqueta \<param> se mostrará en IntelliSense, el Examinador de objetos y en el informe web de comentario de código.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
