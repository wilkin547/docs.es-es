---
title: "Operadores condicionales null (C# y Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operadores condicionales null (C# y Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se utiliza para probar si hay valores null antes de realizar una operación de acceso a miembros \(`?.`\) o índice \(`?[`\).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  
  
```c#  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
```vb  
Dim length = customers?.Length  ‘’ null if customers is null  
Dim first as Customer = customers?(0);  ‘’ null if customers is null  
Dim count as Integer? = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
 El último ejemplo demuestra que los operadores de condición null se están cortocircuitando.  Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.  Seguirán ejecutándose las demás operaciones de menor prioridad en la expresión.  Por ejemplo, `E` en la siguiente siempre se ejecuta y las operaciones `??` y `==` se ejecutan.  
  
```vb-c#  
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
  
```  
  
 Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.  La antigua manera de hacerlo requiere un código parecido a este:  
  
```c#  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…)  
  
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
  
```  
  
 La nueva manera es mucho más sencilla:  
  
```vb-c#  
PropertyChanged?.Invoke(e)  
  
```  
  
 La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en la variable temporal.  
  
 Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.  Había muchas situaciones ambiguas de análisis para permitirlo.  
  
## Especificaciones del lenguaje  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 Para obtener más información, vea la [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)