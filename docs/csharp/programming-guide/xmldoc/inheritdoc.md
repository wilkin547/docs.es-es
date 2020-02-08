---
title: '<inheritdoc>: Guía de programación de C#'
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794838"
---
# <a name="inheritdoc-c-programming-guide"></a>\<inheritdoc> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a>InheritDoc

Herede comentarios XML de clases base, interfaces y métodos similares. Esto elimina la acción de copiar y pegar no deseada de comentarios XML duplicados y mantiene los comentarios XML sincronizados automáticamente. 
  
## <a name="remarks"></a>Comentarios  
Agregue sus comentarios XML en las clases base o las interfaces y deje que InheritDoc copie los comentarios en las clases en implementación.

Agregue sus comentarios XML a los métodos sincrónicos y deje que InheritDoc copie los comentarios en las versiones asincrónicas de los mismos métodos.  

Si quiere copiar los comentarios de un miembro en concreto, puede utilizar el atributo `cref` para especificar el miembro.
  
## <a name="examples"></a>Ejemplos
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
