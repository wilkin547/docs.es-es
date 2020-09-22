---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 471d3ddb5cf5a234cb77de6d1d93309faf754359
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865839"
---
# <a name="summary-visual-basic"></a>\<summary> (Visual Basic)

Especifica el resumen del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parámetros  

 `description`  
 Resumen del objeto.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<summary>` etiqueta para describir un tipo o un miembro de tipo. Use [\<remarks>](remarks.md) para agregar información adicional a una descripción de tipo.  
  
 El texto de la `<summary>` etiqueta es el único origen de información sobre el tipo en IntelliSense y también se muestra en el examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<summary>` etiqueta para describir el `ResetCounter` método y la `Counter` propiedad.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
