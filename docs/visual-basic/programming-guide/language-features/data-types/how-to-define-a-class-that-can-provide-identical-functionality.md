---
title: Procedimiento Definición de clases capaces de proporcionar la misma funcionalidad en tipos de datos diferentes
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 3b1f47250453c32735d633b98da0bd0ddb1ed5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393862"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a>Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes (Visual Basic)
Puede definir una clase desde la que se puedan crear objetos que proporcionen una funcionalidad idéntica en tipos de datos diferentes. Para ello, especifique uno o más *parámetros de tipo* en la definición. Posteriormente, la clase puede servir de plantilla para los objetos que usan distintos tipos de datos. Una clase definida de esta manera se denomina *clase genérica*.  
  
 La ventaja de definir una clase genérica es que se define una sola vez y, después, el código puede usarla para crear muchos objetos que emplean una gran variedad de tipos de datos. El resultado es rendimiento mayor que al definir la clase con el tipo `Object` .  
  
 Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.  
  
### <a name="to-define-a-class-with-a-type-parameter"></a>Para definir una clase con un parámetro de tipo  
  
1. Defina la clase de la manera normal.  
  
2. Agregue `(Of` *typeparameter* `)` inmediatamente después del nombre de clase para especificar un parámetro de tipo.  
  
3. Si tiene más de un parámetro de tipo, realice una lista separada por comas entre paréntesis. No repita la palabra clave `Of` .  
  
4. Si el código realiza operaciones en un parámetro de tipo distintas de la asignación simple, siga ese parámetro de tipo con una cláusula `As` para agregar una o más *restricciones*. Una restricción garantiza que el tipo proporcionado para ese parámetro de tipo satisfaga un requisito como el siguiente:  
  
    - Admitir una operación, como `>`, que realice el código.  
  
    - Admita a un miembro, como un método, al que accede el código.  
  
    - Exponer un constructor sin parámetros.  
  
     Si no especifica ninguna restricción, las únicas operaciones y miembros que el código podrá usar son las que admite el [Object Data Type](../../../language-reference/data-types/object-data-type.md). Para obtener más información, consulta [Type List](../../../language-reference/statements/type-list.md).  
  
5. Identifique cada miembro de clase que se va a declarar con un tipo suministrado y declárelo `As` `typeparameter` . Esto se aplica al almacenamiento interno, los parámetros de procedimiento y los valores devueltos.  
  
6. Asegúrese de que el código solo usa operaciones y métodos admitidos por cualquier tipo de datos que pueda proporcionar a `itemType`.  
  
     En el ejemplo siguiente se define una clase que administra una lista muy simple. Contiene la lista de la matriz interna `items`y el código que la usa puede declarar el tipo de datos de los elementos de la lista. Un constructor con parámetros permite que el código de uso establezca el límite superior de `items` , y el constructor sin parámetros lo establece en 9 (para un total de 10 elementos).  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     Puede declarar una clase de `simpleList` para que contenga una lista de valores `Integer` , otra para que contenga una lista de valores `String` y otra para que contenga valores `Date` . Excepto para el tipo de datos de los miembros de la lista, los objetos creados a partir de todas estas clases se comportan exactamente igual.  
  
     El argumento de tipo que el código que lo usa proporciona a `itemType` puede ser un tipo intrínseco como `Boolean` o `Double`, una estructura, una enumeración o cualquier tipo de clase, incluida una que defina la aplicación.  
  
     Puede probar la clase `simpleList` con el siguiente código.  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos](index.md)
- [Tipos genéricos en Visual Basic](generic-types.md)
- [Independencia del lenguaje y componentes independientes del lenguaje](../../../../standard/language-independence-and-language-independent-components.md)
- [De](../../../language-reference/statements/of-clause.md)
- [Type List](../../../language-reference/statements/type-list.md)
- [Procedimiento Uso de clases genéricas](how-to-use-a-generic-class.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
