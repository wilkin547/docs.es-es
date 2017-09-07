---
title: struct (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- struct_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
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
ms.openlocfilehash: 309e68a57e1ee869850d960ffaac6cf35eb6e260
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="struct-c-reference"></a>struct (Referencia de C#)
Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario. En el siguiente ejemplo se muestra una declaración de struct simple:  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a>Comentarios  
 Los structs también pueden contener [constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constantes](../../../csharp/programming-guide/classes-and-structs/constants.md), [campos](../../../csharp/programming-guide/classes-and-structs/fields.md), [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexadores](../../../csharp/programming-guide/indexers/index.md), [operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [eventos](../../../csharp/programming-guide/events/index.md) y [tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.  
  
 Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
 Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct. Por ese motivo, los miembros de struct no se pueden declarar como `protected`.  
  
 Para obtener más información, vea [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## <a name="examples"></a>Ejemplos  
 Para obtener ejemplos y más información, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tipos](../../../csharp/language-reference/keywords/types.md)   
 [Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])  
 [class](../../../csharp/language-reference/keywords/class.md)   
 [interfaz](../../../csharp/language-reference/keywords/interface.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)

