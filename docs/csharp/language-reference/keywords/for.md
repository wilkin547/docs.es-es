---
title: for (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb7e83733fe026658f502b430975a0f8a27e9df3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="for-c-reference"></a>for (Referencia de C#)
Mediante el uso de un bucle `for`, se puede ejecutar una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`. Este tipo de bucle es útil para recorrer en iteración matrices y para otras aplicaciones en las que se sabe de antemano cuántas veces se quiere recorrer en iteración el bucle.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el valor de `i` se escribe en la consola y se incrementa en 1 durante cada iteración del bucle.  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 La instrucción `for` del ejemplo anterior realiza las siguientes acciones.  
  
1.  Primero, se establece el valor inicial de la variable `i`. Este paso solo se produce una vez, independientemente de cuántas veces se repita el bucle. Esta inicialización se puede considerar que tiene lugar fuera del proceso de bucle.  
  
2.  Para evaluar la condición (`i <= 5`), el valor de `i` se compara con 5.  
  
    -   Si `i` es menor o igual a 5, la condición se evalúa como `true` y se producen las siguientes acciones.  
  
        1.  La instrucción `Console.WriteLine` en el cuerpo del bucle muestra el valor de `i`.  
  
        2.  El valor de `i` se incrementa en 1.  
  
        3.  El bucle vuelve al principio del paso 2 para evaluar la condición de nuevo.  
  
    -   Si `i` es mayor que 5, la condición se evalúa como `false`, y se sale del bucle.  
  
 Tenga en cuenta que, si el valor inicial de `i` es mayor que 5, el cuerpo del bucle no se ejecuta ni siquiera una vez.  
  
 Cada instrucción `for` define secciones de inicializador, condición e iterador. Normalmente estas secciones determinan cuántas veces se repite el bucle.  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 Las secciones tienen los objetivos siguientes.  
  
-   La sección de inicializador establece las condiciones iniciales. Las instrucciones de esta sección se ejecutan solo una vez, antes de entrar en el bucle. La sección solo puede contener una de las dos opciones siguientes.  
  
    -   La declaración e inicialización de una variable de bucle local, como se muestra en el primer ejemplo (`int i = 1`). La variable es local para el bucle y no es accesible desde fuera del bucle.  
  
    -   Ninguna o más expresiones de instrucción de la siguiente lista, separadas por comas.  
  
        -   instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)  
  
        -   invocación de un método  
  
        -   expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`  
  
        -   expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`  
  
        -   creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   expresión [await](../../../csharp/language-reference/keywords/await.md)  
  
-   La sección de condición contiene una expresión booleana que se evalúa para determinar si el bucle debe salir o volverse a ejecutar.  
  
-   La sección de iterador define lo que sucede después de cada iteración del cuerpo del bucle. La sección de iterador contiene ninguna o más de las siguientes expresiones de instrucción, separadas por comas:  
  
    -   instrucción [assignment](../../../csharp/language-reference/operators/assignment-operator.md)  
  
    -   invocación de un método  
  
    -   expresión de [incremento](../../../csharp/language-reference/operators/increment-operator.md) de prefijo o sufijo, como `++i` o `i++`  
  
    -   expresión de [decremento](../../../csharp/language-reference/operators/decrement-operator.md) de prefijo o sufijo, como `--i` o `i--`  
  
    -   creación de un objeto mediante [new](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   expresión [await](../../../csharp/language-reference/keywords/await.md)  
  
-   El cuerpo del bucle consta de una instrucción, una instrucción vacía o un bloque de instrucciones, que se crean incluyendo cero o más instrucciones entre llaves.  
  
     Se puede salir de un bucle `for` mediante la palabra clave [break](../../../csharp/language-reference/keywords/break.md), o bien se puede ir a la siguiente iteración mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md). También se puede salir de un bucle mediante una instrucción [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 En el primer ejemplo de este tema se muestra el tipo de bucle `for` más común, que realiza las siguientes opciones para las secciones.  
  
-   El inicializador declara e inicializa una variable de bucle local, `i`, que mantiene un recuento de las iteraciones del bucle.  
  
-   La condición comprueba el valor de la variable de bucle con un valor final conocido, 5.  
  
-   La sección de iterador usa una instrucción de incremento postfijo, `i++`, para realizar un recuento de cada iteración del bucle.  
  
 En el ejemplo siguiente se muestran varias opciones menos comunes: asignar un valor a una variable de bucle externa en la sección de inicializador, invocar el método `Console.WriteLine` en las secciones de inicializador y de iterador, y cambiar los valores de dos variables en la sección de iterador.  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 Todas las expresiones que definen una instrucción `for` son opcionales. Por ejemplo, la siguiente instrucción crea un bucle infinito.  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [for (Instrucción) (C++)](/cpp/cpp/for-statement-cpp)  
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)
