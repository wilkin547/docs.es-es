---
title: Operadores condicionales null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722158"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. ¿y? operadores condicionales null () (Visual Basic)

Comprueba el valor del operando izquierdo es null (`Nothing`) antes de realizar un acceso a miembros (`?.`) o un índice (`?()`) devuelve la operación; `Nothing` si el operando izquierdo se evalúa como `Nothing`. Tenga en cuenta que, en las expresiones que normalmente devolvería los tipos de valor, el operador condicional null devuelve un <xref:System.Nullable%601>.

Estos operadores ayudan a escribir menos código para controlar las comprobaciones de valores null, especialmente cuando descender en estructuras de datos. Por ejemplo:

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional null es:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Los operadores de condición NULL se cortocircuitan.  Si una operación en una cadena de las operaciones de índice y de acceso de miembro condicional devuelve Nothing, se detiene el resto de la ejecución de la cadena.  En el ejemplo siguiente, c (e) no se evalúa si `A`, `B`, o `C` se evalúa como Nothing.

```vb
A?.B?.C?(E);
```

Otro uso de acceso a miembros condicional null es invocar delegados de manera segura para subprocesos con mucho menos código.  La antigua manera de hacerlo requiere un código parecido a este:  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

La nueva manera es mucho más sencilla:  

```vb
PropertyChanged?.Invoke(…)
```

La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal. Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.  

## <a name="see-also"></a>Vea también

- [Operadores (Visual Basic)](index.md)
- [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)
