---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352257"
---
# <a name="remarks-visual-basic"></a>\<Comentarios > (Visual Basic)
Especifica una sección de comentarios para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del miembro.  
  
## <a name="remarks"></a>Comentarios  
 Use la etiqueta `<remarks>` para agregar información sobre un tipo, complementando la información especificada con [\<> de Resumen](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Esta información aparece en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<remarks>` para explicar lo que hace el método `UpdateRecord`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
