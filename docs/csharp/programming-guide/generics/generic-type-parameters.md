---
title: Parámetros de tipos genéricos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 35029b90fb7b905a87055596cf8dcd6a84ef9d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332473"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Parámetros de tipos genéricos (Guía de programación de C#)
En un tipo genérico o en una definición de método, un parámetro de tipo es un marcador de posición para un tipo específico que un cliente especifica cuando crean instancias de una variable del tipo genérico. Una clase genérica, como `GenericList<T>` que se muestra en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md), no puede usarse como está porque no es realmente un tipo; es más parecida a un plano para un tipo. Para usar `GenericList<T>`, el código cliente debe declarar y crear instancias de un tipo construido especificando un argumento de tipo dentro de corchetes angulares. El argumento de tipo de esta clase determinada puede ser cualquier tipo reconocido por el compilador. Puede crearse cualquier número de instancias de tipo construidas, usando cada una un argumento de tipo diferente, de la manera siguiente:  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 En cada una de estas instancias de `GenericList<T>`, cada aparición de `T` en la clase se sustituirá en tiempo de ejecución con el argumento de tipo. Mediante esta sustitución, hemos creado tres objetos eficaces y con seguridad de tipos independientes con una definición de clase única. Para obtener más información sobre cómo se realiza esta sustitución mediante CLR, vea [Genéricos en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Instrucciones de nomenclatura de los parámetros de tipo  
  
-   **Asigne** nombres descriptivos a los parámetros de tipo genérico, a no ser que un nombre de una sola letra sea completamente claro y un nombre descriptivo no agregue ningún valor.  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   **Considere** el uso de T como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   **Establezca** el prefijo "T" a los nombres de parámetro de tipo descriptivos.  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   **Considere** la posibilidad de indicar restricciones que se encuentran en un parámetro de tipo en el nombre del parámetro. Por ejemplo, un parámetro restringido a `ISession` puede llamarse `TSession`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Genéricos](../../../csharp/programming-guide/generics/index.md)  
 [Diferencias entre plantillas de C++ y tipos genéricos de C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
