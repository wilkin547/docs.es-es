---
title: Tipos anónimos (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 451fe45c9b5efbeb64b1066d6ba8e5f9b27300c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="anonymous-types-visual-basic"></a>Tipos anónimos (Visual Basic)
Visual Basic admite tipos anónimos, que le permiten crear objetos sin escribir una definición de clase para el tipo de datos. En su lugar, el compilador genera una clase. La clase no tiene ningún nombre utilizable, hereda directamente de <xref:System.Object>y contiene las propiedades especificadas al declarar el objeto. Dado que no se especifica el nombre del tipo de datos, se conoce como un *tipo anónimo*.  
  
 En el ejemplo siguiente se declara y crea la variable `product` como una instancia de un tipo anónimo que tiene dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 A *expresión de consulta* usa tipos anónimos para combinar las columnas de datos seleccionadas por una consulta. No se puede definir el tipo del resultado de antemano, porque no se puede predecir las columnas que se puede seleccionar una consulta determinada. Tipos anónimos permiten escribir una consulta que selecciona cualquier número de columnas, en cualquier orden. El compilador crea un tipo de datos que coincida con las propiedades especificadas y el orden especificado.  
  
 En los ejemplos siguientes, `products` es una lista de objetos de producto, cada uno de los cuales tiene muchas propiedades. Variable `namePriceQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo que tiene dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 Variable `nameQuantityQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo que tiene dos propiedades, `Name` y `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 Para obtener más información sobre el código creado por el compilador para un tipo anónimo, vea [definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  El nombre del tipo anónimo es el compilador genera y puede variar de una compilación a otra. El código no debe usar o se basan en el nombre de un tipo anónimo porque el nombre podría cambiar cuando se vuelve a compilar un proyecto.  
  
## <a name="declaring-an-anonymous-type"></a>Declarar un tipo anónimo  
 La declaración de una instancia de un tipo anónimo utiliza una lista de inicializadores para especificar las propiedades del tipo. Puede especificar solo las propiedades cuando se declaran un tipo anónimo, no otros elementos de clase como métodos o eventos. En el ejemplo siguiente, `product1` es una instancia de un tipo anónimo que tiene dos propiedades: `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 Si designa las propiedades como propiedades de clave, se puede utilizar para comparar dos instancias de tipo anónimo son iguales. Sin embargo, no se puede cambiar los valores de las propiedades de clave. Consulte la sección de propiedades de clave más adelante en este tema para obtener más información.  
  
 Observe que la declaración de una instancia de un tipo anónimo es como la declaración de una instancia de un tipo con nombre usando un inicializador de objeto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 Para obtener más información sobre otras maneras de especificar las propiedades de tipo anónimo, vea [Cómo: deducir los nombres de propiedad y los tipos en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Propiedades clave  
 Propiedades de clave son distintas de las propiedades de clave no en varios aspectos fundamentales:  
  
-   Solo los valores de las propiedades de clave se comparan con el fin de determinar si dos instancias son iguales.  
  
-   Los valores de las propiedades de clave son de solo lectura y no se puede cambiar.  
  
-   Solo los valores de propiedad de clave están incluidos en el algoritmo de código hash generado por el compilador para un tipo anónimo.  
  
### <a name="equality"></a>Igualdad  
 Instancias de tipos anónimos pueden ser iguales solo si son instancias del mismo tipo anónimo. El compilador trata las dos instancias como instancias del mismo tipo si cumplen las condiciones siguientes:  
  
-   Se declaran en el mismo ensamblado.  
  
-   Sus propiedades tienen los mismos nombres, los mismos tipos deducidos y se declaran en el mismo orden. Las comparaciones de nombres no distinguen mayúsculas de minúsculas.  
  
-   Las mismas propiedades en cada una se marcan como propiedades de clave.  
  
-   Al menos una propiedad de cada declaración es una propiedad clave.  
  
 Una instancia de un tipo anónimo que no tiene ninguna propiedad clave es igual solo a sí mismo.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 Dos instancias del mismo tipo anónimo son iguales si los valores de sus propiedades claves son iguales. Los ejemplos siguientes muestran cómo se comprueba la igualdad.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### <a name="read-only-values"></a>Valores de solo lectura  
 No se puede cambiar los valores de las propiedades de clave. Por ejemplo, en `prod8` en el ejemplo anterior, el `Name` y `Price` campos son `read-only`, pero `OnHand` puede cambiarse.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Tipos anónimos de expresiones de consulta  
 Las expresiones de consulta no siempre requieren la creación de tipos anónimos. Cuando sea posible, usan un tipo existente para almacenar los datos de columna. Esto se produce cuando la consulta devuelve los registros completos desde el origen de datos o sólo un campo de cada registro. En los siguientes ejemplos de código, `customers` es una colección de objetos de un `Customer` clase. La clase tiene muchas propiedades y puede incluir uno o varios de ellos en el resultado de la consulta, en cualquier orden. En los dos primeros ejemplos, no hay tipos anónimos son necesarias porque las consultas seleccionan los elementos de tipos con nombre:  
  
-   `custs1` contiene una colección de cadenas, porque `cust.Name` es una cadena.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2` contiene una colección de `Customer` objetos, dado que cada elemento de `customers` es un `Customer` objeto y todo el elemento está seleccionado por la consulta.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 Sin embargo, los tipos con nombre adecuados no están siempre disponibles. Puede seleccionar los nombres de cliente y direcciones para un propósito, números de Id. de cliente y ubicaciones de la otra y los nombres de cliente, direcciones e historiales de orden para una tercera. Tipos anónimos permiten seleccionar cualquier combinación de propiedades, en cualquier orden, sin declarar primero un nuevo tipo con nombre que contenga el resultado. En su lugar, el compilador crea un tipo anónimo para cada compilación de propiedades. La siguiente consulta selecciona sólo el cliente nombre y número de identificación de cada uno `Customer` objeto `customers`. Por lo tanto, el compilador crea un tipo anónimo que contiene sólo esas dos propiedades.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 Los nombres y los tipos de datos de las propiedades del tipo anónimo se toman de los argumentos de `Select`, `cust.Name` y `cust.ID`. Las propiedades de un tipo anónimo creado por una consulta siempre son propiedades de clave. Cuando `custs3` se ejecuta en la siguiente `For Each` bucles, el resultado es una colección de instancias de un tipo anónimo con dos propiedades de clave, `Name` y `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 Los elementos de la colección representada por `custs3` están fuertemente tipados, y puede usar IntelliSense para navegar por las propiedades disponibles y comprobar sus tipos.  
  
 Para obtener más información, consulte [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Decidir entre usar tipos anónimos  
 Antes de crear un objeto como una instancia de una clase anónima, tenga en cuenta si ése es la mejor opción. Por ejemplo, si desea crear un objeto temporal para que contenga datos relacionados y no tiene necesidad de otros campos y métodos que puede contener una clase completa, un tipo anónimo es una buena solución. Tipos anónimos también resultan prácticos si desea una selección diferente de propiedades para cada declaración o si desea cambiar el orden de las propiedades. Sin embargo, si el proyecto incluye varios objetos que tienen las mismas propiedades, en un orden fijo, puede declararlos más fácilmente mediante el uso de un tipo con nombre con un constructor de clase. Por ejemplo, con un constructor adecuado, es más fácil declarar varias instancias de un `Product` clase superior al declarar varias instancias de un tipo anónimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 Otra ventaja de tipos con nombre es que el compilador puede detectar un error ortográfico accidental de un nombre de propiedad. En los ejemplos anteriores, `firstProd2`, `secondProd2`, y `thirdProd2` están pensados para ser instancias del mismo tipo anónimo. Sin embargo, si fuera a accidentalmente declare `thirdProd2` en una de las siguientes formas, su tipo sería diferente de `firstProd2` y `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 Lo que es más importante, existen limitaciones en el uso de tipos anónimos que no se aplican a las instancias de tipos con nombre. `firstProd2`, `secondProd2`, y `thirdProd2` son instancias del mismo tipo anónimo. Sin embargo, el nombre del tipo anónimo compartido no está disponible y no puede aparecer donde se espera un nombre de tipo en el código. Por ejemplo, un tipo anónimo no puede utilizarse para definir una firma de método para declarar otra variable o campo o en cualquier declaración de tipo. Como resultado, los tipos anónimos no son adecuados cuando deba compartir información a través de métodos.  
  
## <a name="an-anonymous-type-definition"></a>Una definición de tipo anónimo  
 En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas.  
  
 Si el tipo anónimo contiene al menos una propiedad de clave, la definición invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, y <xref:System.Object.ToString%2A>. El código generado para probar la igualdad y determinar que el valor de código hash tiene en cuenta sólo las propiedades de clave. Si el tipo anónimo no contiene ninguna propiedad clave, solo <xref:System.Object.ToString%2A> se invalida. Propiedades con nombre explícito de un tipo anónimo no se pueden entrar en conflicto con estos métodos generados. Es decir, no puede usar `.Equals`, `.GetHashCode`, o `.ToString` a un nombre de propiedad.  
  
 Las definiciones de tipo anónimo que tengan al menos una propiedad clave también implementan la <xref:System.IEquatable%601?displayProperty=nameWithType> interfaz, donde `T` es el tipo del tipo anónimo.  
  
 Para obtener más información sobre el código creado por el compilador y la funcionalidad de los métodos invalidados, vea [definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Vea también  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
