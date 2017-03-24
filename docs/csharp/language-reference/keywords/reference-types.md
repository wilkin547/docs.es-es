---
title: "Tipos de referencia (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.referencetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, tipos de referencia"
  - "tipos de referencia [C#]"
  - "tipos [C#], tipos de referencia"
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Tipos de referencia (Referencia de C#)
Hay dos clases de tipos en C\#: tipos de referencia y tipos de valor.  Las variables de tipos de referencia almacenan referencias en sus datos \(objetos\), mientras que las variables de tipos de valor contienen directamente los datos.  Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.  Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra \(excepto en el caso de las variables de parámetro ref y out, consulte [ref](../../../csharp/language-reference/keywords/ref.md) y [Modificador del parámetro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)\).  
  
 Las palabras clave siguientes se usan para declarar tipos de referencia:  
  
-   [clase](../../../csharp/language-reference/keywords/class.md)  
  
-   [interfaz](../../../csharp/language-reference/keywords/interface.md)  
  
-   [delegado](../../../csharp/language-reference/keywords/delegate.md)  
  
 C\# también proporciona los siguientes tipos de referencia integrados:  
  
-   [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [object](../../../csharp/language-reference/keywords/object.md)  
  
-   [string](../../../csharp/language-reference/keywords/string.md)  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)