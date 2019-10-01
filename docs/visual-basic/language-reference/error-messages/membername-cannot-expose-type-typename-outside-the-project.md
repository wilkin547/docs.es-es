---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: ca67e74d7790352bd1842cb8a59fe1525af6e18c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700894"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>' \<membername > ' no puede exponer el tipo ' \<typename > ' fuera del proyecto a través de \<containertype > ' \<containertypename > '
Una variable, un parámetro de procedimiento o un valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.  
  
 El código esqueleto siguiente muestra una situación que genera este error.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara `Protected`, `Friend`, `Protected Friend` o `Private` está pensado para tener acceso limitado fuera del contexto de declaración. Si se usa como el tipo de datos de una variable con acceso menos restringido, se anularía este propósito. En el código de esqueleto anterior, `exposedVar` es `Public` y expondría @no__t 2 al código que no debe tener acceso a él.  
  
 **IDENTIFICADOR de error:** BC30909  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambie el nivel de acceso de la variable, el parámetro de procedimiento o la función que debe ser al menos tan restrictivo como el nivel de acceso de su tipo de datos.  
  
## <a name="see-also"></a>Vea también

- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
