---
title: <summary> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 0fbe07884f55b7e6f460929e54520de5f718e1af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940769"
---
# <a name="summary-visual-basic"></a>\<Resumen > (Visual Basic)
Especifica el resumen del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Resumen del objeto.  
  
## <a name="remarks"></a>Comentarios  
 Use el `<summary>` etiquetas para describir un tipo o un miembro de tipo. Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.  
  
 El texto para el `<summary>` etiqueta es la única fuente de información sobre el tipo en IntelliSense y también se muestra en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<summary>` etiquetas para describir el `ResetCounter` método y `Counter` propiedad.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
