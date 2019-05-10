---
title: Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9f24dd2a20dc3a4935cd288a20a0e12c1d47bee1
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912340"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial
Un `For Each` bucle utiliza una matriz como su *elemento* variable de iteración, pero inicializa esa matriz.  
  
 Las instrucciones siguientes muestran cómo se puede generar este error.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 La primera `For Each` instrucción es la manera correcta de tener acceso a elementos de `arrayList`. El segundo `For Each` instrucción genera este error.  
  
 **Identificador de error:** BC32039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la inicialización de la declaración de la *elemento* variable de iteración.  
  
## <a name="see-also"></a>Vea también

- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Colecciones](../../../standard/collections/index.md)
