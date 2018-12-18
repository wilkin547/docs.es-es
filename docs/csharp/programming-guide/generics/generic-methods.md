---
title: 'Métodos genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 28ce14eca4398a359061a54b7c6cc74ed69b87b1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244822"
---
# <a name="generic-methods-c-programming-guide"></a>Métodos genéricos (Guía de programación de C#)
Un método genérico es un método que se declara con parámetros de tipo, de la manera siguiente:  
  
 [!code-csharp[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]  
  
 En el siguiente ejemplo de código se muestra una manera de llamar al método con `int` para el argumento de tipo:  
  
 [!code-csharp[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]  
  
 También puede omitir el argumento de tipo y el compilador lo deducirá. La siguiente llamada a `Swap` es equivalente a la llamada anterior:  
  
 [!code-csharp[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]  
  
 Las mismas reglas para la inferencia de tipos se aplican a los métodos estáticos y a los métodos de instancia. El compilador puede deducir los parámetros de tipo basados en los argumentos de método que se pasan; no puede deducir los parámetros de tipo solo desde un valor devuelto o una restricción. Por lo tanto, la inferencia de tipos no funciona con métodos que no tienen parámetros. La inferencia de tipos se produce en tiempo de compilación antes de que el compilador intente resolver las firmas de método sobrecargadas. El compilador aplica la lógica de inferencia de tipos a todos los métodos genéricos que comparten el mismo nombre. En el paso de resolución de sobrecarga, el compilador incluye solo esos métodos genéricos en los que la inferencia de tipos se ha realizado correctamente.  
  
 Dentro de una clase genérica, los métodos no genéricos pueden tener acceso a los parámetros de tipo de nivel de clase, de la manera siguiente:  
  
 [!code-csharp[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]  
  
 Si define un método genérico que toma los mismos parámetros de tipo que la clase contenedora, el compilador genera la advertencia CS0693 porque dentro del ámbito del método, el argumento que se ha proporcionado para el `T` interno oculta el argumento que se ha proporcionado para el `T` externo. Si necesita la flexibilidad de llamar a un método de la clase genérica con argumentos de tipo diferentes de los que se han proporcionado cuando se ha creado una instancia de la clase, considere la posibilidad de proporcionar otro identificador para el parámetro de tipo del método, como se muestra en `GenericList2<T>` en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]  
  
 Use restricciones para permitir operaciones más especializadas en parámetros de tipo de métodos. Esta versión de `Swap<T>`, ahora denominada `SwapIfGreater<T>`, solo puede usarse con argumentos de tipo que implementan <xref:System.IComparable%601>.  
  
 [!code-csharp[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]  
  
 Los métodos genéricos pueden sobrecargarse en varios parámetros de tipo. Por ejemplo, todos los métodos siguientes pueden ubicarse en la misma clase:  
  
 [!code-csharp[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 Para obtener más información, consulte la [Especificación del lenguaje C#](~/_csharplang/spec/classes.md#methods).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)
