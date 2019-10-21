---
title: <typeparam> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: e5e0d7be46e02bd30799b54246db729ae63ca300
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523288"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam> (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Una descripción del parámetro de tipo.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo. Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.  
  
 Para más información, vea [Genéricos](../generics/index.md).  
  
 El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).  
  
 Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
