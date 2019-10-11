---
title: Los parámetros de tipo no se pueden utilizar como calificadores
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250338"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Los parámetros de tipo no se pueden utilizar como calificadores

Un elemento de programación está calificado con una cadena de calificación que incluye un parámetro de tipo.

Un parámetro de tipo representa un requisito para un tipo que se va a proporcionar cuando se construya el tipo genérico. No representa un tipo definido específico. Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.

El código siguiente puede generar este error:

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 **IDENTIFICADOR de error:** BC32098  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Quite el parámetro de tipo de la cadena de calificación o reemplácelo por un tipo definido.  
  
2. Si necesita usar un tipo construido para buscar el elemento de programación que se va a calificar, debe usar la lógica de programa adicional.  
  
## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Lista de tipos](../statements/type-list.md)
