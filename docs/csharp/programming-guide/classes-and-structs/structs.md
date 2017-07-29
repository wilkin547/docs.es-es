---
title: "Structs (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a>Structs (Guía de programación de C#)
Los structs se definen mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md), por ejemplo:  
  
 [!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 Los structs comparten la mayoría de la sintaxis con las clases, aunque están más limitados que estas:  
  
-   Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como constantes o estáticos.  
  
-   Un struct no puede declarar un constructor predeterminado (un constructor sin parámetros) ni un finalizador.  
  
-   Los structs se copian en la asignación. Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original. Es importante que lo recuerde al trabajar con colecciones de tipos de valor como Dictionary\<string, myStruct>.  
  
-   Los structs son tipos de valor y las clases son tipos de referencia.  
  
-   A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.  
  
-   Los structs pueden declarar constructores que tengan parámetros.  
  
-   Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Todos los structs heredan directamente de `System.ValueType`, que hereda de `System.Object`.  
  
-   Un struct puede implementar interfaces.  
  
-   Un struct se puede usar como un tipo que acepta valores NULL y se le puede asignar un valor NULL.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)

