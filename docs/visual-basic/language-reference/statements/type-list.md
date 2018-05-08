---
title: Lista de tipos (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-list-visual-basic"></a>Lista de tipos (Visual Basic)
Especifica la *parámetros de tipo* para un *genérico* elemento de programación. Varios parámetros se separan mediante comas. A continuación se muestra la sintaxis para un parámetro de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`genericmodifier`|Opcional. Puede usarse solo en interfaces y delegados genéricos. Puede declarar un tipo covariante mediante la [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) palabra clave o contravariante utilizando la [en](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) (palabra clave). Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|  
|`typename`|Requerido. Nombre del parámetro de tipo. Se trata de un marcador de posición, que será sustituido por un tipo definido proporcionado por el argumento de tipo correspondiente.|  
|`constraintlist`|Opcional. Lista de requisitos que restringe el tipo de datos que se pueden proporcionar para `typename`. Si tiene varias restricciones, encierre entre llaves (`{ }`) y sepárelas con comas. Debe introducir la lista de restricciones con la [como](../../../visual-basic/language-reference/statements/as-clause.md) (palabra clave). Usa `As` una sola vez, al principio de la lista.|  
  
## <a name="remarks"></a>Comentarios  
 Cada elemento de programación genérico debe tomar al menos un parámetro de tipo. Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico. Puede definir una clase genérica, estructura, interfaz, procedimiento o delegado.  
  
 Para obtener más información sobre cuándo se debe definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Para obtener más información sobre nombres de parámetros de tipo, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Paréntesis.** Si se proporciona una lista de parámetros de tipo, debe encerrarlo entre paréntesis y debe introducir la lista con el [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Usa `Of` una sola vez, al principio de la lista.  
  
-   **Restricciones.** Una lista de *restricciones* en un tipo de parámetro puede incluir los elementos siguientes en cualquier combinación:  
  
    -   Cualquier número de interfaces. El tipo proporcionado debe implementar cada interfaz en esta lista.  
  
    -   Al menos una clase. El tipo proporcionado debe heredar de esa clase.  
  
    -   Palabra clave `New`. El tipo proporcionado debe exponer un constructor sin parámetros al que puede tener acceso su tipo genérico. Esto es útil si restringe un parámetro de tipo por una o varias interfaces. Un tipo que implementa las interfaces no expone necesariamente un constructor, y según el nivel de acceso de un constructor, el código dentro del tipo genérico no pueda tener acceso a él.  
  
    -   Ya sea la `Class` palabra clave o el `Structure` (palabra clave). El `Class` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la sea un tipo de referencia, por ejemplo una cadena, matriz o delegado, o un objeto creado a partir de una clase. El `Structure` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a la sea un tipo de valor, por ejemplo una estructura, enumeración o datos elementales escriba. No se puede incluir tanto `Class` y `Structure` en el mismo `constraintlist`.  
  
     El tipo proporcionado debe satisfacer cada requisito que se incluya en `constraintlist`.  
  
     Restricciones de cada parámetro de tipo son independientes de las restricciones de otros tipos de parámetros.  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Sustitución de tiempo de compilación.** Cuando se crea un tipo construido de un elemento de programación genérico, proporciona un tipo definido para cada parámetro de tipo. El compilador de Visual Basic sustituye el tipo proporcionado para todas las apariciones de `typename` dentro del elemento genérico.  
  
-   **Si no existen restricciones.** Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y los miembros admitidos por el [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) para ese parámetro de tipo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un esquema de definición de una clase de diccionario genérico, incluida una función esquemática para agregar una nueva entrada al diccionario.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Dado que `dictionary` es genérico, el código que lo usa puede crear una variedad de objetos del mismo, cada uno tiene la misma funcionalidad pero que actúa en un tipo de datos diferente. En el ejemplo siguiente se muestra una línea de código que crea un `dictionary` objeto con `String` entradas y `Integer` claves.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el esquema de definición equivalente generado por el ejemplo anterior.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Tipo de objeto de datos](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
