---
title: 'Pasar parámetros de tipo de valor: Guía de programación de C#'
description: Cuando se pasa una variable de tipo de valor a un método por valor en C#, los cambios no tienen ningún efecto en los datos originales. Para cambiar el valor, pase por referencia.
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: 84829722cfb0b7ce71aff36f27a7c97cfa07ad5e
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864701"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a>Pasar parámetros de tipo de valor (Guía de programación de C#)
Una variable [tipo de valor](../../language-reference/builtin-types/value-types.md) contiene sus datos directamente, en oposición a la variable [tipo de referencia](../../language-reference/keywords/reference-types.md), que contiene una referencia a sus datos. Pasar una variable tipo de valor a un método en función del valor significa pasar una copia de la variable al método. Ningún cambio realizado en el parámetro dentro del método afecta a los datos originales almacenados en la variable de argumentos. Si desea que el método al que se llama cambie el valor del argumento, debe pasarlo en función de la referencia, con la palabra clave [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md). También puede usar la palabra clave [in](../../language-reference/keywords/in-parameter-modifier.md) para pasar un parámetro de valor por referencia para evitar la copia, a la vez que se asegura de que el valor no se modificará. Para simplificar, en el ejemplo siguiente se usa `ref`.  
  
## <a name="passing-value-types-by-value"></a>Pasar tipos de valor en función del valor  
 En el ejemplo siguiente se muestra cómo pasar los parámetros de tipo de valor en función del valor. La variable `n` se pasa en función del valor al método `SquareIt`. Los cambios que tienen lugar dentro del método no tienen ningún efecto en el valor original de la variable.  
  
 [!code-csharp[csProgGuideParameters#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#3)]  
  
 La variable `n` es un tipo de valor. Contiene sus datos, el valor `5`. Cuando se invoca `SquareIt`, el contenido de `n` se copia en el parámetro `x`, que se multiplica dentro del método. En `Main`, sin embargo, el valor de `n` es el mismo después de llamar al método`SquareIt` que el que era antes. El cambio que tiene lugar dentro del método solo afecta a la variable local `x`.  
  
## <a name="passing-value-types-by-reference"></a>Pasar tipos de valor en función de la referencia  
 El ejemplo siguiente es el mismo que el anterior, salvo que el argumento se pasa como un parámetro `ref`. El valor del argumento subyacente, `n`, se cambia cuando se modifica `x` en el método.  
  
 [!code-csharp[csProgGuideParameters#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#4)]  
  
 En este ejemplo, no es el valor de `n` el que se pasa, sino una referencia a `n`. El parámetro `x` no es un [entero](../../language-reference/builtin-types/integral-numeric-types.md); se trata de una referencia a `int`, en este caso, una referencia a `n`. Por tanto, cuando `x` se multiplica dentro del método, lo que realmente se multiplica es a lo que `x` hace referencia, `n`.  
  
## <a name="swapping-value-types"></a>Intercambiar tipos de valor  
 Un ejemplo común de modificación de valores de argumentos es un método de intercambio, donde se pasan dos variables al método, y el método intercambia su contenido. Debe pasar los argumentos al método de intercambio en función de la referencia. De lo contrario, se intercambian copias locales de los parámetros dentro del método, y no se produce ningún cambio en el método de llamada. En el ejemplo siguiente se intercambian valores enteros.  
  
 [!code-csharp[csProgGuideParameters#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#5)]  
  
 Al llamar al método `SwapByRef`, use la palabra clave `ref` en la llamada, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideParameters#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#6)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Pasar parámetros](./passing-parameters.md)
- [Pasar parámetros Reference-Type](./passing-reference-type-parameters.md)
