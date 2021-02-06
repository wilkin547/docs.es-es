---
description: 'Más información acerca de: <returns> (Visual Basic)'
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: ba5f1e231502a67e86ffbb92cf8868c3aecb05d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640386"
---
# <a name="returns-visual-basic"></a>\<returns> (Visual Basic)

Especifica el valor devuelto de la propiedad o función.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a>Parámetros  

 `description`  
 Descripción del valor devuelto.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<returns>` etiqueta del comentario para una declaración de método para describir el valor devuelto.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<returns>` etiqueta para explicar lo que `DoesRecordExist` devuelve la función.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
