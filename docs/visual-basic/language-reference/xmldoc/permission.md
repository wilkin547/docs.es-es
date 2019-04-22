---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7333d4a4d051c157f6732224da0fffe4d7cd35ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827671"
---
# <a name="permission-visual-basic"></a>\<permiso > (Visual Basic)
Especifica un permiso necesario para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Parámetros  
 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML. Incluya `member` entre comillas ("").  
  
 `description`  
 Descripción del acceso al miembro.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<permission>` etiqueta para documentar el acceso de un miembro. Use la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<permission>` etiquetas para describir que el <xref:System.Security.Permissions.FileIOPermission> requerido por la `ReadFile` método.  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
