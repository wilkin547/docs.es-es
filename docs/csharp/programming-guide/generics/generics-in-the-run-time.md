---
title: "Genéricos en el motor en tiempo de ejecución (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 661dff2d8ec2e12ab6a459660a5378f74e93b9c5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-in-the-run-time-c-programming-guide"></a>Genéricos en el motor en tiempo de ejecución (Guía de programación de C#)
Cuando se compila un tipo o método genérico en el lenguaje intermedio de Microsoft (MSIL), contiene metadatos que lo identifican como poseedor de parámetros de tipo. La forma en que se usa MSIL para un tipo genérico depende de si el parámetro de tipo proporcionado es un tipo de valor o de referencia.  
  
 Cuando se construye por primera vez un tipo genérico con un tipo de valor como parámetro, el motor de ejecución crea un tipo genérico especializado sustituyendo el parámetro o los parámetros proporcionados en los lugares adecuados del MSIL. Los tipos genéricos especializados se crean una vez para cada tipo de valor único que se usa como parámetro.  
  
 Por ejemplo, suponga que el código de su programa ha declarado una pila compuesta por enteros:  
  
 [!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]  
  
 En este momento, el motor de ejecución genera una versión especializada de la clase <xref:System.Collections.Generic.Stack%601> sustituyendo el entero adecuadamente para su parámetro. Ahora, cada vez que el código de su programa use una pila de enteros, el motor en tiempo de ejecución vuelve a usar la clase especializada generada <xref:System.Collections.Generic.Stack%601>. En el ejemplo siguiente, se crean dos instancias de una pila de enteros y comparten una instancia única del código `Stack<int>`:  
  
 [!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]  
  
 En cambio, suponga que otra clase <xref:System.Collections.Generic.Stack%601> con un tipo de valor diferente, como un `long` o una estructura definida por el usuario como parámetro, se crea en otro punto del código. Como resultado, el motor de ejecución genera otra versión del tipo genérico y sustituye un `long` en los lugares apropiados en el MSIL. Las conversiones ya no son necesarias porque cada clase genérica especializada contiene de forma nativa el tipo de valor.  
  
 Los genéricos funcionan de forma ligeramente distinta para los tipos de referencia. Cuando se construye un tipo genérico por primera vez con un tipo de referencia, el motor en tiempo de ejecución crea un tipo genérico especializado sustituyendo las referencias a objetos para los parámetros del MSIL. Después, cada vez que se crea una instancia de un tipo construido con un tipo de referencia como parámetro, independientemente del tipo que sea, el motor de ejecución vuelve a usar la versión especializada del tipo genérico previamente creada. Esto es posible porque todas las referencias son del mismo tamaño.  
  
 Por ejemplo, suponga que tiene dos tipos de referencia, una clase `Customer` y una clase `Order`, y que ha creado una pila de tipos `Customer`:  
  
 [!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]  
  
 [!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]  
  
 En este punto, el motor de ejecución genera una versión especializada de la clase <xref:System.Collections.Generic.Stack%601> que, en lugar de almacenar los datos, almacena referencias a objetos que se rellenarán más tarde. Suponga que la línea siguiente de código crea una pila de otro tipo de referencia, que se denomina `Order`:  
  
 [!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]  
  
 A diferencia de lo que sucede con los tipos de valor, no se crea otra versión especializada de la clase <xref:System.Collections.Generic.Stack%601> para el tipo `Order`. En su lugar, se crea una instancia de la versión especializada de la clase <xref:System.Collections.Generic.Stack%601> y se establece la variable `orders` para hacer referencia a ella. Suponga que encuentra una línea de código para crear una pila de tipo `Customer`:  
  
 [!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]  
  
 Como con el uso anterior de la clase <xref:System.Collections.Generic.Stack%601> creada usando el tipo `Order`, se crea otra instancia de la clase especializada <xref:System.Collections.Generic.Stack%601>. Los punteros contenidos allí se establecen para hacer referencia a un área de memoria del tamaño de un tipo `Customer`. Dado que el número de tipos de referencia puede variar significativamente de un programa a otro, la implementación de genéricos de C# reduce significativamente la cantidad de código limitando a uno el número de clases especializadas creadas por el compilador para las clases genéricas de tipos de referencia.  
  
 Además, cuando se crea una instancia de una clase de C# genérica mediante un parámetro de tipo de valor o de referencia se puede consultar en tiempo de ejecución mediante reflexión, y se puede comprobar tanto su tipo real como su parámetro de tipo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Genéricos](~/docs/standard/generics/index.md)

