---
title: "'<membername>' no puede exponer el tipo '<typename>' fuera del proyecto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 03767501488a395073f925e27adea439751c0de6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265069"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<membername >' no puede exponer el tipo '\<typename >' fuera del proyecto mediante \<containertype > '\<containertypename >'
Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.  
  
 La estructura de código siguiente muestra una situación que genera este error.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración. Lo utilizan como los datos de tipo de una variable con acceso menos restringido iría con este fin. En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debería tener acceso a él.  
  
 **Identificador de error:** BC30909  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nivel de acceso de la variable, parámetro de procedimiento o función que se devuelven para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.  
  
## <a name="see-also"></a>Vea también
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
