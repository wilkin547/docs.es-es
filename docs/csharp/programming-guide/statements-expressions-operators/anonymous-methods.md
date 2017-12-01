---
title: "Métodos anónimos (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4d942e0f3245f6404c896173b2c7ca6f1090a8c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-methods-c-programming-guide"></a>Métodos anónimos (Guía de programación de C#)
En las versiones de C# anteriores a 2.0, la única manera de declarar un [delegado](../../../csharp/language-reference/keywords/delegate.md) era usar [métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md). C# 2.0 introdujo los métodos anónimos y en C# 3.0 y versiones posteriores, las expresiones lambda reemplazan a los métodos anónimos como la manera preferida de escribir código en línea. En cambio, la información sobre los métodos anónimos de este tema también se aplica a las expresiones lambda. Existe un caso en el que un método anónimo proporciona funciones que no se encuentran en las expresiones lambda. Los métodos anónimos le permiten omitir la lista de parámetros. Esto significa que un método anónimo puede convertirse en delegados con una variedad de firmas. Esto no es posible con las expresiones lambda. Para obtener más información específica sobre las expresiones lambda, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Crear métodos anónimos es básicamente una manera de pasar un bloque de código como un parámetro de delegado. Dos ejemplos:  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 Mediante los métodos anónimos, reduce la sobrecarga de codificación al crear instancias de delegados porque no tiene que crear un método independiente.  
  
 Por ejemplo, especificar un bloque de código en lugar de un delegado puede ser útil en una situación en la que tener que crear un método puede parecer una sobrecarga innecesaria. Un buen ejemplo sería cuando inicia un nuevo subproceso. Esta clase crea un subproceso y también contiene el código que el subproceso ejecuta sin crear un método adicional para el delegado.  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a>Comentarios  
 El ámbito de los parámetros de un método anónimo es el *bloque de método anónimo*.  
  
 Es un error tener una instrucción de salto, como [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), dentro del bloque de método anónimo si el destino está fuera del bloque. También es un error tener una instrucción de salto, como `goto`, `break` o `continue`, fuera del bloque de método anónimo si el destino está dentro del bloque.  
  
 Las variables locales y los parámetros cuyo ámbito contiene una declaración de método anónimo se denominan variables *externas* del método anónimo. Por ejemplo, en el siguiente segmento de código, `n` es una variable externa:  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 Una referencia a la variable externa `n` se dice que está *capturada* cuando se crea el delegado. A diferencia de las variables locales, la duración de una variable capturada se extiende hasta que los delegados que hacen referencia a los métodos anónimos son aptos para la recolección de elementos no utilizados.  
  
 Un método anónimo no puede tener acceso a los parámetros [ref](../../../csharp/language-reference/keywords/ref.md) u [out](../../../csharp/language-reference/keywords/out.md) de un ámbito externo.  
  
 No se puede tener acceso a ningún código no seguro dentro del *bloque de método anónimo*.  
  
 Los métodos anónimos no se permiten en el lado izquierdo del operador [is](../../../csharp/language-reference/keywords/is.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran dos maneras de crear instancias de un delegado:  
  
-   Asociar el delegado con un método anónimo.  
  
-   Asociar el delegado con un método con nombre (`DoWork`).  
  
 En cada caso, se muestra un mensaje cuando se invoca al delegado.  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Delegados](../../../csharp/programming-guide/delegates/index.md)  
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Delegados con métodos con nombre y delegados con métodos anónimos](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
