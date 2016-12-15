---
title: "Tipos de valor (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.valuetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, tipos de valor"
  - "tipos [C#], tipos de valor"
  - "tipos de valor [C#]"
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tipos de valor (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los tipos de valor consisten en dos categorías principales:  
  
-   [Structs](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Enumeraciones](../../../csharp/language-reference/keywords/enum.md)  
  
 Los structs se dividen en las siguientes categorías:  
  
-   Tipos numéricos  
  
    -   [Tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Tipos de punto flotante](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Structs definidos por el usuario.  
  
## Características principales de los tipos de valor  
 Variables que están basadas directamente en tipos de valor que contienen valores.  La asignación de una variable de tipo de valor a otra copia el valor contenido.  Esto es diferente de la asignación de variables de tipo de referencia, que copia una referencia en el objeto pero no el propio objeto.  
  
 Todos los tipos de valor se derivan implícitamente de la clase <xref:System.ValueType?displayProperty=fullName>.  
  
 A diferencia de los tipos de referencia, no es posible derivar un nuevo tipo de un tipo de valor.  No obstante, al igual que los tipos de referencia, los structs pueden implementar interfaces.  
  
 A diferencia de los tipos de referencia, los tipos de valor no pueden contener el valor `null`.  Sin embargo, la característica [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) permite que los tipos de valor se asignarán a `null`.  
  
 Cada tipo de valor tiene un constructor implícito predeterminado que inicializa el valor predeterminado de ese tipo.  Para obtener información acerca de los valores predeterminados de los tipos de valor, consulte [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## Características principales de los tipos simples  
 Todos los tipos simples \(aquellos que forman parte integral del lenguaje C\#\) son alias de los tipos del sistema .NET Framework.  Por ejemplo, [int](../../../csharp/language-reference/keywords/int.md) es un alias de <xref:System.Int32?displayProperty=fullName>.  Para una lista completa de alias, vea [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Las expresiones constantes, cuyos operandos son todos constantes de tipos simples, se evalúan en tiempo de compilación.  
  
 Los tipos simples se pueden inicializar mediante literales.  Por ejemplo, 'A' es un literal del tipo `char` y 2001 es un literal del tipo `int`.  
  
## Inicializar tipos de valor  
 Las variables locales de C\# deben inicializarse para poder utilizarse.  Por ejemplo, podría declarar una variable local sin inicialización, como en el ejemplo siguiente:  
  
```  
int myInt;  
```  
  
 No se podrá utilizar hasta que se inicialice.  La inicialización se puede realizar mediante la siguiente instrucción:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Esta instrucción es equivalente a la siguiente instrucción:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 También se puede realizar la declaración y la inicialización en la misma instrucción, tal y como se muestra en los siguientes ejemplos:  
  
```  
int myInt = new int();  
```  
  
 O bien  
  
```  
int myInt = 0;  
```  
  
 Con el operador [new](../../../csharp/language-reference/keywords/new.md), se realiza una llamada al constructor predeterminado del tipo específico y se asigna el valor predeterminado a la variable.  En el ejemplo anterior, el constructor predeterminado asigna a `myInt` el valor `0`.  Para obtener más información acerca de los valores asignados mediante constructores predeterminados, consulte [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Con los tipos definidos por el usuario, se utiliza [new](../../../csharp/language-reference/keywords/new.md) para invocar el constructor predeterminado.  Por ejemplo, la siguiente instrucción invoca el constructor predeterminado del struct `Point`:  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Después de esta llamada, el struct se considera definitivamente asignada; es decir, todos sus miembros se inicializan con sus valores predeterminados.  
  
 Para obtener más información acerca del operador new, consulte [new](../../../csharp/language-reference/keywords/new.md).  
  
 Para obtener información acerca de cómo dar formato a la presentación de tipos numéricos, consulte [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)