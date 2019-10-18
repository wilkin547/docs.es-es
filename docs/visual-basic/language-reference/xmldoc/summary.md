---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524633"
---
# <a name="summary-visual-basic"></a>\<summary > (Visual Basic)
Especifica el resumen del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Resumen del objeto.  
  
## <a name="remarks"></a>Comentarios  
 Use la etiqueta `<summary>` para describir un tipo o un miembro de tipo. Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.  
  
 El texto de la etiqueta `<summary>` es el único origen de información sobre el tipo en IntelliSense y también se muestra en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<summary>` para describir el método `ResetCounter` y la propiedad `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
