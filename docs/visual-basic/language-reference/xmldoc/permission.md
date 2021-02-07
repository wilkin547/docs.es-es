---
description: 'Más información acerca de: <permission> (Visual Basic)'
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7a227e97051002c834c96297d3028f08e3ed07ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700265"
---
# <a name="permission-visual-basic"></a>\<permission> (Visual Basic)

Especifica un permiso necesario para el miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Parámetros  

 `member`  
 Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML. Encerrar entre comillas `member` ("").  
  
 `description`  
 Descripción del acceso al miembro.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<permission>` etiqueta para documentar el acceso de un miembro. Utilice la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<permission>` etiqueta para describir que el <xref:System.Security.Permissions.FileIOPermission> método requiere `ReadFile` .  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
