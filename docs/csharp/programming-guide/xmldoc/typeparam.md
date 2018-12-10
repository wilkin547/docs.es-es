---
title: '&lt;typeparam&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5db257cc655b7d9112fc4efc917f5d2175fcf665
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143121"
---
# <a name="lttypeparamgt-c-programming-guide"></a>&lt;typeparam&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `name`  
 El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Una descripción del parámetro de tipo.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo. Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.  
  
 Para más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).  
  
 El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
