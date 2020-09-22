---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 70078752495240ab8c72fe1bbecdca554166fb22
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866423"
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
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<remarks>` etiqueta para explicar lo que `UpdateRecord` hace el método.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
