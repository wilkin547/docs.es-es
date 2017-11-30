---
title: Operadores condicionales null (C# y Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95b4079cf4e71c0ef9cd436ec230337f512229a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="null-conditional-operators-c-and-visual-basic"></a>Operadores condicionales null (C# y Visual Basic)
Se utiliza para probar si hay valores null antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[`).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  
  
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
  
 El último ejemplo demuestra que los operadores de condición null se están cortocircuitando.  Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.  Seguirán ejecutándose las demás operaciones de menor prioridad en la expresión.  Por ejemplo, `E` en la siguiente operación se ejecuta en la segunda línea y las operaciones `??` y `==` se ejecutan.  En la primera línea, `??` se cortocircuita y `E` no se ejecuta cuando el lado izquierdo se evalúa como no null.
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
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
  
 Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.  Había muchas situaciones ambiguas de análisis para permitirlo.  
  
## <a name="language-specifications"></a>Especificaciones del lenguaje  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Para obtener más información, vea [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>Vea también  
 [?? (operador de uso combinado de null)](null-conditional-operator.md)  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)  
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)
