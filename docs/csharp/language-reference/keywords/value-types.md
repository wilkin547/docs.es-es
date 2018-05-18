---
title: Tipos de valor (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: fdda6942c6883baaaea5e305a1e699a01e707d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="value-types-c-reference"></a>Tipos de valor (Referencia de C#)
Los tipos de valor constan de dos categorías principales:  
  
-   [Structs](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Enumeraciones](../../../csharp/language-reference/keywords/enum.md)  
  
 Los structs se dividen en estas categorías:  
  
-   Tipos numéricos  
  
    -   [Tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Tipos de punto flotante](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Structs definidos por el usuario.  
  
## <a name="main-features-of-value-types"></a>Características principales de los tipos de valor  
 Las variables que se basan en tipos de valor directamente contienen valores. Asignar una variable de tipo de valor a otra copia el valor incluido. Esto difiere de la asignación de variables de tipo de referencia, que copia una referencia al objeto pero no el propio objeto.  
  
 Todos los tipos de valor se derivan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>.  
  
 A diferencia de los tipos de referencia, no puede derivar un tipo nuevo de un tipo de valor. En cambio, como los tipos de referencia, los structs pueden implementar interfaces.  
  
 A diferencia de los tipos de referencia, un tipo de valor no puede contener el valor `null`. En cambio, la característica [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) se permite para los tipos de valor que se van a asignar a `null`.  
  
 Cada tipo de valor tiene un constructor predeterminado implícito que inicializa el valor predeterminado de ese tipo. Para obtener información sobre los valores predeterminados de los tipos de valor, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## <a name="main-features-of-simple-types"></a>Características principales de los tipos simples  
 Todos los tipos simples, integrales del lenguaje de C#, son alias de los tipos de sistema de .NET Framework. Por ejemplo, [int](../../../csharp/language-reference/keywords/int.md) es un alias de <xref:System.Int32?displayProperty=nameWithType>. Para obtener una lista completa de los alias, vea [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Las expresiones constantes, cuyos operandos son todos constantes de tipo simple, se evalúan en tiempo de compilación.  
  
 Los tipos simples pueden inicializarse mediante el uso de literales. Por ejemplo, "A" es un literal del tipo `char` y 2001 es un literal del tipo `int`.  
  
## <a name="initializing-value-types"></a>Inicializar tipos de valor  
 Las variables locales en C# deben inicializarse antes de usarse. Por ejemplo, puede declarar una variable local sin inicialización como en el ejemplo siguiente:  
  
```  
int myInt;  
```  
  
 No puede usarla antes de inicializarla. Puede inicializarla con la siguiente instrucción:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Esta instrucción es equivalente a la instrucción siguiente:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Por supuesto, puede tener la declaración y la inicialización en la misma instrucción como en los ejemplos siguientes:  
  
```  
int myInt = new int();  
```  
  
 -O bien-  
  
```  
int myInt = 0;  
```  
  
 Con el operador [new](../../../csharp/language-reference/keywords/new.md) se llama al constructor predeterminado del tipo específico y asigna el valor predeterminado a la variable. En el ejemplo anterior, el constructor predeterminado ha asignado el valor `0` a `myInt`. Para obtener más información sobre los valores que se han asignado llamando a los constructores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Con los tipos definidos por el usuario, use [new](../../../csharp/language-reference/keywords/new.md) para invocar al constructor predeterminado. Por ejemplo, la siguiente instrucción invoca al constructor predeterminado del struct `Point`:  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Después de esta llamada, el struct se considera asignado definitivamente; es decir, todos sus miembros se inicializan a sus valores predeterminados.  
  
 Para obtener más información sobre el operador new, vea [new](../../../csharp/language-reference/keywords/new.md).  
  
 Para obtener información sobre cómo aplicar formato al resultado de los tipos numéricos, vea [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)
