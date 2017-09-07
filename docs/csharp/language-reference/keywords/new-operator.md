---
title: new (Operador, Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
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
ms.openlocfilehash: 59e1cc2006548df9a7a10283a34044040e5c2fef
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="new-operator-c-reference"></a>new (Operador, Referencia de C#)
Se usa para crear objetos e invocar constructores. Por ejemplo:  
  
```  
Class1 obj  = new Class1();  
```  
  
 También se usa para crear instancias de tipos anónimos:  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 El operador `new` también se usa para invocar el constructor predeterminado para tipos de valor. Por ejemplo:  
  
```  
int i = new int();  
```  
  
 En la instrucción anterior, `i` se ha inicializado en `0`, que es el valor predeterminado para el tipo `int`. La instrucción tiene el mismo efecto que lo siguiente:  
  
```  
int i = 0;  
```  
  
 Para obtener una lista completa de valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Recuerde que es un error declarar un constructor predeterminado para una [struct](../../../csharp/language-reference/keywords/struct.md), ya que cada tipo de valor tiene implícitamente un constructor predeterminado público. Es posible declarar constructores parametrizados en un tipo struct para establecer sus valores iniciales, pero esto solo es necesario si se requieren valores distintos de los predeterminados.  
  
 Los objetos de tipo de valor (como los structs) se crean en la pila, mientras que los objetos de tipo de referencia (como las clases) se crean en el montón. Ambos tipos de objetos se destruyen automáticamente, pero los objetos basados en tipos de valor se destruyen cuando salen del ámbito, mientras que los objetos basados en tipos de referencia se destruyen en un momento no especificado después de que se haya quitado la última referencia a ellos. En el caso de los tipos de referencia que consumen recursos fijos, como grandes cantidades de memoria, identificadores de archivo o conexiones de red, a veces es conveniente emplear la finalización determinista para asegurarse de que el objeto se destruya en cuanto sea posible. Para obtener más información, vea [Instrucción using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 El operador `new` no se puede sobrecargar.  
  
 Si el operador `new` no puede asignar memoria, se produce la excepción <xref:System.OutOfMemoryException>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se crean y se inicializan un objeto `struct` y un objeto de clase mediante el operador `new` y, después, se les asignan valores. Se muestran el valor predeterminado y los valores asignados.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 Observe en el ejemplo que el valor predeterminado de una cadena es `null`. Por lo tanto, no se muestra.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

