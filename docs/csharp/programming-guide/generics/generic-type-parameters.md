---
title: "Parámetros de tipos genéricos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
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
ms.openlocfilehash: ce1024215a381afb3a7b42f2127fe5e8c212d378
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generic-type-parameters-c-programming-guide"></a>Parámetros de tipos genéricos (Guía de programación de C#)
En un tipo genérico o en una definición de método, un parámetro de tipo es un marcador de posición para un tipo específico que un cliente especifica cuando crean instancias de una variable del tipo genérico. Una clase genérica, como `GenericList<T>` que se muestra en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md), no puede usarse como está porque no es realmente un tipo; es más parecida a un plano para un tipo. Para usar `GenericList<T>`, el código cliente debe declarar y crear instancias de un tipo construido especificando un argumento de tipo dentro de corchetes angulares. El argumento de tipo de esta clase determinada puede ser cualquier tipo reconocido por el compilador. Puede crearse cualquier número de instancias de tipo construidas, usando cada una un argumento de tipo diferente, de la manera siguiente:  
  
 [!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 En cada una de estas instancias de `GenericList<T>`, cada aparición de `T` en la clase se sustituirá en tiempo de ejecución con el argumento de tipo. Mediante esta sustitución, hemos creado tres objetos eficaces y con seguridad de tipos independientes con una definición de clase única. Para obtener más información sobre cómo se realiza esta sustitución mediante CLR, vea [Genéricos en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Instrucciones de nomenclatura de los parámetros de tipo  
  
-   **Asigne** nombres descriptivos a los parámetros de tipo genérico, a no ser que un nombre de una sola letra sea completamente claro y un nombre descriptivo no agregue ningún valor.  
  
     [!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   **Considere** el uso de T como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.  
  
     [!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   **Establezca** el prefijo "T" a los nombres de parámetro de tipo descriptivos.  
  
     [!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   **Considere** la posibilidad de indicar restricciones que se encuentran en un parámetro de tipo en el nombre del parámetro. Por ejemplo, un parámetro restringido a `ISession` puede llamarse `TSession`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Genéricos](../../../csharp/programming-guide/generics/index.md)   
 [Diferencias entre plantillas de C++ y tipos genéricos de C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)

