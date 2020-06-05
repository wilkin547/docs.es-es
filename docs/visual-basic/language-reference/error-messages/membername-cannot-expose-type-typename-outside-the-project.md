---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397290"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<membername>' no puede exponer el tipo '\<typename>' fuera del proyecto mediante \<containertype> '\<containertypename>'
Una variable, un parámetro de procedimiento o un valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.  
  
 El código esqueleto siguiente muestra una situación que genera este error.  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara `Protected` , `Friend` , `Protected Friend` o `Private` está pensado para tener acceso limitado fuera del contexto de declaración. Si se usa como el tipo de datos de una variable con acceso menos restringido, se anularía este propósito. En el código de esqueleto anterior, `exposedVar` es `Public` y se expondría `privateClass` al código que no debe tener acceso a él.  
  
 **Identificador de error:** BC30909  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambie el nivel de acceso de la variable, el parámetro de procedimiento o la función que debe ser al menos tan restrictivo como el nivel de acceso de su tipo de datos.  
  
## <a name="see-also"></a>Consulte también

- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
