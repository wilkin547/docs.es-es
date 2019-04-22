---
title: El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: b798f296b62b51de34a7ec5ce5a8b608273f5748
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819234"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
No se puede inferir un nombre de miembro de tipo anónimo en una expresión compleja.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Para obtener más información acerca de los orígenes desde el que los tipos anónimos pueden y no pueden deducir tipos y nombres de miembro, vea [Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Identificador de error:** BC36556  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asigne la expresión a un nombre de miembro, como se muestra en el código siguiente:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Vea también

- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Cómo: Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
