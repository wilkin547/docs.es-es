---
title: Structs (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322993"
---
# <a name="structs-c-programming-guide"></a>Structs (Guía de programación de C#)
Los structs se definen mediante la palabra clave [struct](../../../csharp/language-reference/keywords/struct.md), por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
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
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)
