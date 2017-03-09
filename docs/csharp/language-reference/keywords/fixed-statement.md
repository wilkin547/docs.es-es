---
title: "fixed (Instrucci&#243;n, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "fixed_CSharpKeyword"
  - "fixed"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "fixed (palabra clave) [C#]"
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# fixed (Instrucci&#243;n, Referencia de C#)
La instrucción `fixed` evita que el recolector de elementos no utilizados vuelva a ubicar una variable móvil.  La instrucción `fixed` solo se permite en un contexto [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  `Fixed` también se puede utilizar para crear [búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante la ejecución de la instrucción.  Sin la instrucción `fixed`, los punteros a variables administradas móviles serían de poca utilidad, ya que el proceso de recolección de elementos no utilizados podría cambiar la ubicación de las variables de forma impredecible.  El compilador de C\# sólo permite asignar un puntero a una variable administrada en una instrucción `fixed`.  
  
 [!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#1)]  
  
 Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo, o la dirección de una variable.  En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas variables.  Para obtener más información sobre los búferes de tamaño fijo, vea [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 [!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#2)]  
  
 Se pueden inicializar varios punteros a la vez, siempre que sean del mismo tipo.  
  
```  
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```  
  
 Para inicializar punteros de tipos distintos, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#3)]  
  
 Después de ejecutar el código de la instrucción, se desancla cualquier variable anteriormente anclada y queda sujeta al proceso de recolección de elementos no utilizados.  Por lo tanto, no se debe apuntar a esas variables desde fuera de la instrucción `fixed`.  
  
> [!NOTE]
>  Los punteros inicializados en instrucciones fixed no se pueden modificar.  
  
 En el modo no seguro \(unsafe\), se puede asignar memoria a la pila, donde no está sometida a recolección de elementos no utilizados y, por lo tanto, no necesita anclarse.  Para obtener más información, vea [stackalloc \(Referencia de C\#\)](../../../csharp/language-reference/keywords/stackalloc.md).  
  
## Ejemplo  
 [!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefFixedLock/csrefKeywordsFixedLock.cs#4)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [no seguras](../../../csharp/language-reference/keywords/unsafe.md)   
 [Búferes de tamaño fijo](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)