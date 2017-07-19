---
title: "Pasar parámetros de tipo de valor (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: b0735f9a42fad01695c1ad64cfb937dce8e3cb93
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a>Pasar parámetros de tipo de valor (Guía de programación de C#)
Una variable [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) contiene sus datos directamente, en oposición a la variable [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md), que contiene una referencia a sus datos. Pasar una variable tipo de valor a un método en función del valor significa pasar una copia de la variable al método. Ningún cambio realizado en el parámetro dentro del método afecta a los datos originales almacenados en la variable de argumentos. Si desea que el método al que se llama cambie el valor del parámetro, debe pasarlo en función de la referencia, con la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md). Para simplificar, en el ejemplo siguiente se usa `ref`.  
  
## <a name="passing-value-types-by-value"></a>Pasar tipos de valor en función del valor  
 En el ejemplo siguiente se muestra cómo pasar los parámetros de tipo de valor en función del valor. La variable `n` se pasa en función del valor al método `SquareIt`. Los cambios que tienen lugar dentro del método no tienen ningún efecto en el valor original de la variable.  
  
 [!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 La variable `n` es un tipo de valor. Contiene sus datos, el valor `5`. Cuando se invoca `SquareIt`, el contenido de `n` se copia en el parámetro `x`, que se multiplica dentro del método. En `Main`, sin embargo, el valor de `n` es el mismo después de llamar al método`SquareIt` que el que era antes. El cambio que tiene lugar dentro del método solo afecta a la variable local `x`.  
  
## <a name="passing-value-types-by-reference"></a>Pasar tipos de valor en función de la referencia  
 El ejemplo siguiente es el mismo que el anterior, salvo que el argumento se pasa como un parámetro `ref`. El valor del argumento subyacente, `n`, se cambia cuando se modifica `x` en el método.  
  
 [!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 En este ejemplo, no es el valor de `n` el que se pasa, sino una referencia a `n`. El parámetro `x` no es un [entero](../../../csharp/language-reference/keywords/int.md); se trata de una referencia a `int`, en este caso, una referencia a `n`. Por tanto, cuando `x` se multiplica dentro del método, lo que realmente se multiplica es a lo que `x` hace referencia, `n`.  
  
## <a name="swapping-value-types"></a>Intercambiar tipos de valor  
 Un ejemplo común de modificación de valores de argumentos es un método de intercambio, donde se pasan dos variables al método, y el método intercambia su contenido. Debe pasar los argumentos al método de intercambio en función de la referencia. De lo contrario, se intercambian copias locales de los parámetros dentro del método, y no se produce ningún cambio en el método de llamada. En el ejemplo siguiente se intercambian valores enteros.  
  
 [!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 Al llamar al método `SwapByRef`, use la palabra clave `ref` en la llamada, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Pasar parámetros Reference-Type](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)
