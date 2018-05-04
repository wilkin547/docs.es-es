---
title: Operadores condicionales null (C# y Visual Basic)
ms.date: 04/03/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ffeaa3c2088d0bb2c000704cfe312b0f9453b68
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. y ?[]: operadores condicionales NULL (C# y Visual Basic)
Se utiliza para probar si hay valores null antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[]`).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Los operadores de condición NULL se cortocircuitan.  Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.  En el ejemplo siguiente, `E` no se ejecuta si `A`, `B` o `C` se evalúan como NULL.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.  La antigua manera de hacerlo requiere un código parecido a este:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 La nueva manera es mucho más sencilla:  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.  
  
 Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.  
  
## <a name="language-specifications"></a>Especificaciones del lenguaje  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Para obtener más información, vea [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>Vea también  
 [?? (operador de uso combinado de NULL)](null-conditional-operator.md)  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)  
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
