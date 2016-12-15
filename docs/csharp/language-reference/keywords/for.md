---
title: "for (Referencia de C#) | Microsoft Docs"
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
  - "for"
  - "for_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "for (palabra clave) [C#]"
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
caps.handback.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# for (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Mediante un bucle `for` , puede ejecutar una instrucción o un bloque de instrucciones varias veces hasta que una expresión especificada se evalúe con `false`.  Esta clase de bucle es útil para recorrer en iteración las matrices y para otras aplicaciones en las que se sabe de antemano cuántas veces se desea el bucle para recorrer.  
  
## Ejemplo  
 En el ejemplo siguiente, el valor `i` se escribe en la consola y se incrementa en 1 en cada iteración del bucle.  
  
 [!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 La instrucción `for` en el ejemplo anterior realiza las acciones siguientes.  
  
1.  Primero, el valor inicial `i` variable se establece.  Este paso solamente pasa una vez, independientemente de cuántas veces repite el bucle.  Puede pensar en esta inicialización como suceso fuera del proceso del Bucle.  
  
2.  Para evaluar la condición \(`i <= 5`\), el valor `i` se compara con 5.  
  
    -   Si `i` es menor o igual que 5, la condición se evalúa como `true`, y las acciones siguientes.  
  
        1.  La instrucción `Console.WriteLine` en el cuerpo del bucle muestra el valor `i`.  
  
        2.  El valor `i` se incrementa en 1.  
  
        3.  El bucle vuelve al inicio del paso 2 de evaluar la condición de nuevo.  
  
    -   Si `i` es mayor que 5, la condición se evalúa como `false`, y a sale del bucle.  
  
 Observe que, si el valor inicial `i` es mayor que 5, el cuerpo del bucle no se ejecuta incluso una vez.  
  
 Cada instrucción `for` define el inicializador, la condición, y secciones de iterador.  Estas secciones determinan normalmente cuántas veces recorre el bucle.  
  
```c#  
for (initializer; condition; iterator)  
    body  
```  
  
 Las secciones responden a los siguientes propósitos.  
  
-   La sección de inicializadores fija las condiciones iniciales.  Las instrucciones de esta sección sólo se ejecutan una vez, antes de escribir el bucle.  La sección puede contener sólo una de las dos opciones siguientes.  
  
    -   La declaración y la inicialización de una variable de bucle local, como el primer ejemplo muestra \(`int i = 1`\).  La variable es local al bucle y no se puede tener acceso desde fuera del bucle.  
  
    -   Cero o más expressons de la instrucción de la lista siguiente, separados por comas.  
  
        -   Instrucción de[asignación](../../../csharp/language-reference/operators/assignment-operator.md)  
  
        -   invocación de un método  
  
        -   expresión [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`  
  
        -   expresión [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`  
  
        -   creación de un objeto mediante [nuevo](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   expresión de[espera](../../../csharp/language-reference/keywords/await.md)  
  
-   La sección de la condición contiene una expresión booleana que se evalúa para determinar si el bucle debe salir o se debe ejecutar de nuevo.  
  
-   La sección de iterador define qué ocurre después de cada iteración del cuerpo del bucle.  La sección de iterador contiene cero o más de las expresiones siguientes de la instrucción, separados por comas:  
  
    -   Instrucción de[asignación](../../../csharp/language-reference/operators/assignment-operator.md)  
  
    -   invocación de un método  
  
    -   expresión [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`  
  
    -   expresión [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`  
  
    -   creación de un objeto mediante [nuevo](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   expresión de[espera](../../../csharp/language-reference/keywords/await.md)  
  
-   El cuerpo del bucle consiste en una instrucción, una instrucción vacía, o un bloque de instrucciones, que se crea agregando cero o más instrucción entre llaves.  
  
     Puede interrumpir un bucle `for` mediante la palabra clave [interrupción](../../../csharp/language-reference/keywords/break.md) , o puede ir a la siguiente iteración mediante la palabra clave [continúe](../../../csharp/language-reference/keywords/continue.md) .  También puede dejar un bucle utilizando [indicado](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), o la instrucción [captura](../../../csharp/language-reference/keywords/throw.md) .  
  
 El primer ejemplo de este tema muestra la forma más habitual de bucle `for` , que toma decisiones siguientes para las secciones.  
  
-   El inicializador declarar e inicializar una variable de bucle local, `i`, que mantiene un recuento de las iteraciones del bucle.  
  
-   Las comprobaciones de condición el valor de la variable de bucle con un valor final conocido, 5.  
  
-   La sección de iterador utiliza una instrucción de incremento de sufijo, `i++`, marque cada iteración del bucle.  
  
 El ejemplo siguiente muestra varias menos opciones comunes: asignando un valor a una variable externa de bucle en la sección de inicializadores, invocando el método `Console.WriteLine` en el inicializador y las secciones de iterador, y cambiar los valores de dos variables en la sección del iterador.  
  
 [!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 Todas las expresiones que definen una instrucción `for` son opcionales.  Por ejemplo, la siguiente instrucción crea un bucle infinito.  
  
 [!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [for \(Instrucción\) \(C\+\+\)](/visual-cpp/cpp/for-statement-cpp)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)