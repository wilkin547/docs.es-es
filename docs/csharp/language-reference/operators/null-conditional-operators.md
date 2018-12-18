---
title: 'Operadores condicionales NULL: Referencia de C#'
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 4189b07fd280192a4cb39400e4e77cef702c9d08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239558"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. y ?[]: operadores condicionales NULL (C# y Visual Basic)
Comprueba si el valor del operando izquierdo es null antes de realizar una operación de acceso a miembro (`?.`) o de índice (`?[]`); devuelve `null` si el operando izquierdo se evalúa como `null`. 

Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 Los operadores de condición NULL se cortocircuitan.  Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.  En el ejemplo siguiente, `E` no se ejecuta si `A`, `B` o `C` se evalúan como NULL.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.  La antigua manera de hacerlo requiere un código parecido a este:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 La nueva manera es mucho más sencilla:  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal. Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.  
  
## <a name="language-specifications"></a>Especificaciones del lenguaje  

Para obtener más información, vea la sección [Operador condicional de NULL](~/_csharplang/spec/expressions.md#null-conditional-operator) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- [?? (operador de uso combinado de NULL)](null-coalescing-operator.md)  
- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
