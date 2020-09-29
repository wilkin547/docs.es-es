---
title: 'Pasar parámetros Reference-Type: Guía de programación de C#'
description: Cuando se pasa un parámetro de tipo de referencia por valor en C#, los datos del objeto al que se hace referencia pueden cambiar, pero no el valor de la propia referencia.
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
ms.openlocfilehash: 315c1193de12a8fb5c066e023bb98bc228ce85bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91154124"
---
# <a name="passing-reference-type-parameters-c-programming-guide"></a>Pasar parámetros Reference-Type (Guía de programación de C#)

Una variable de un [tipo de referencia](../../language-reference/keywords/reference-types.md) no contiene sus datos directamente, contiene una referencia a sus datos. Al pasar un parámetro de tipo de referencia por valor, es posible cambiar los datos que pertenecen al objeto al que se hace referencia, como el valor de un miembro de clase. En cambio, no se puede cambiar el valor de la propia referencia; por ejemplo, no puede usar la misma referencia para asignar memoria para un nuevo objeto y hacer que persista fuera del método. Para ello, pase el parámetro mediante las palabras clave [ref](../../language-reference/keywords/ref.md) u [out](../../language-reference/keywords/out-parameter-modifier.md). Para simplificar, en el ejemplo siguiente se usa `ref`.  
  
## <a name="passing-reference-types-by-value"></a>Pasar tipos de referencia en función del valor  

 En el ejemplo siguiente, se muestra cómo pasar un parámetro de tipo de referencia, `arr`, en función del valor a un método, `Change`. Dado que el parámetro es una referencia a `arr`, es posible cambiar los valores de los elementos de matriz. En cambio, el intento de volver a asignar el parámetro a otra ubicación de memoria solo funciona dentro del método y no afecta a la variable original, `arr`.  
  
 [!code-csharp[csProgGuideParameters#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#7)]  
  
 En el ejemplo anterior, la matriz, `arr`, que es un tipo de referencia, se pasa al método sin el parámetro `ref`. En tal caso, se pasa al método una copia de la referencia, que apunta a `arr`. El resultado muestra que es posible que el método cambie el contenido de un elemento de matriz, en este caso de `1` a `888`. En cambio, si se asigna una nueva porción de memoria al usar el operador [new](../../language-reference/operators/new-operator.md) dentro del método `Change`, la variable `pArray` hace referencia a una nueva matriz. Por tanto, cualquier cambio que hubiese después no afectará a la matriz original, `arr`, que se ha creado dentro de `Main`. De hecho, se crean dos matrices en este ejemplo, una dentro de `Main` y otra dentro del método `Change`.  
  
## <a name="passing-reference-types-by-reference"></a>Pasar tipos de referencia en función de la referencia  

 El ejemplo siguiente es el mismo que el anterior, salvo que la palabra clave `ref` se agrega a la llamada y al encabezado de método. Los cambios que tengan lugar en el método afectan a la variable original en el programa que realiza la llamada.  
  
 [!code-csharp[csProgGuideParameters#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#8)]  
  
 Todos los cambios que tienen lugar dentro del método afectan a la matriz original en `Main`. De hecho, la matriz original se reasigna mediante el operador `new`. Por tanto, después de llamar al método `Change`, cualquier referencia a `arr` apunta a la matriz de cinco elementos, que se crea en el método `Change`.  
  
## <a name="swapping-two-strings"></a>Intercambiar dos cadenas  

 Intercambiar cadenas es un buen ejemplo de pasar parámetros de tipo de referencia en función de la referencia. En el ejemplo, se inicializan dos cadenas, `str1` y `str2`, en `Main` y se pasan al método `SwapStrings` como parámetros modificados por la palabra clave `ref`. Las dos cadenas se intercambian dentro del método y también dentro de `Main`.  
  
 [!code-csharp[csProgGuideParameters#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#9)]  
  
 En este ejemplo, los parámetros tienen que pasarse en función de la referencia para afectar a las variables en el programa que realiza la llamada. Si quita la palabra clave `ref` tanto del encabezado de método como de la llamada al método, no se llevará a cabo ningún cambio en el programa que realiza la llamada.  
  
 Para obtener más información sobre las cadenas, vea [string](../../language-reference/builtin-types/reference-types.md).  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Pasar parámetros](./passing-parameters.md)
- [ref](../../language-reference/keywords/ref.md)
- [in](../../language-reference/keywords/in-parameter-modifier.md)
- [out](../../language-reference/keywords/out.md)
- [Tipos de referencia](../../language-reference/keywords/reference-types.md)
