---
title: "C&#243;mo: Utilizar punteros para copiar una matriz de bytes (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "matrices [C#], byte"
  - "matrices de bytes [C#]"
  - "punteros [C#], para copiar bytes"
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# C&#243;mo: Utilizar punteros para copiar una matriz de bytes (Gu&#237;a de programaci&#243;n de C#)
En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.  
  
 En este ejemplo se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), lo que permite utilizar punteros en el método `Copy`.  La instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) se utiliza para declarar punteros a las matrices de origen y destino.  Así se *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados.  Los bloques de memoria de las matrices no están anclados cuando se completa el bloque `fixed`.  Dado que el método `Copy` de este ejemplo usa la palabra clave `unsafe`, debe compilarse con la opción del compilador **\/unsafe**.  Para establecer la opción en Visual Studio, haga clic con el botón secundario en el nombre de proyecto y, a continuación, haga clic en **Propiedades**.  En la pestaña **Compilación**, seleccione **Permitir código no seguro**.  
  
## Ejemplo  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#3)]  
  
 [!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#18)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [\/unsafe \(Enable Unsafe Mode\)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)