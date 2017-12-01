---
title: "&lt;example&gt; (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c1e08789b8ea7afaa549229968bf53758ce24be3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltexamplegt-c-programming-guide"></a>&lt;example&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Una descripción del ejemplo de código.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<example> le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](../../../csharp/programming-guide/xmldoc/code.md).  
  
 Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/example_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
