---
title: El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701227"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
No se puede inferir un nombre de miembro de tipo anónimo a partir de una expresión compleja.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Para obtener más información sobre los orígenes de los que los tipos anónimos pueden y no pueden inferir nombres y tipos de miembros, vea [How para: Inferir nombres y tipos de propiedades en declaraciones de tipos anónimos @ no__t-0.  
  
 **IDENTIFICADOR de error:** BC36556  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asigne la expresión a un nombre de miembro, como se muestra en el código siguiente:  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Vea también

- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Cómo: Inferir nombres y tipos de propiedades en declaraciones de tipos anónimos @ no__t-0
