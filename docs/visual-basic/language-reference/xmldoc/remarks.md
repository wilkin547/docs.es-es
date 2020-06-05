---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400026"
---
# <a name="remarks-visual-basic"></a>\<remarks> (Visual Basic)
Especifica una sección de comentarios para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del miembro.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<remarks>` etiqueta para agregar información sobre un tipo, complementando la información especificada con [\<summary>](summary.md) .  
  
 Esta información aparece en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<remarks>` etiqueta para explicar lo que `UpdateRecord` hace el método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
