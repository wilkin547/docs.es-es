---
title: Tipos anónimos
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 064c43274069be3951f816eaafafac0bbece7651
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347156"
---
# <a name="anonymous-types-visual-basic"></a>Tipos anónimos (Visual Basic)
Visual Basic admite tipos anónimos, que permiten crear objetos sin escribir una definición de clase para el tipo de datos. En su lugar, el compilador genera una clase. La clase no tiene ningún nombre utilizable, hereda directamente de <xref:System.Object>y contiene las propiedades que se especifican para declarar el objeto. Dado que no se especifica el nombre del tipo de datos, se hace referencia a él como un *tipo anónimo*.  
  
 En el siguiente ejemplo se declaran y crean `product` variables como una instancia de un tipo anónimo que tiene dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Una *expresión de consulta* utiliza tipos anónimos para combinar columnas de datos seleccionados por una consulta. No se puede definir el tipo del resultado de antemano porque no se pueden predecir las columnas que puede seleccionar una consulta determinada. Los tipos anónimos permiten escribir una consulta que selecciona cualquier número de columnas, en cualquier orden. El compilador crea un tipo de datos que coincide con las propiedades especificadas y el orden especificado.  
  
 En los ejemplos siguientes, `products` es una lista de objetos product, cada uno de los cuales tiene muchas propiedades. La variable `namePriceQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo que tiene dos propiedades, `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 La variable `nameQuantityQuery` contiene la definición de una consulta que, cuando se ejecuta, devuelve una colección de instancias de un tipo anónimo que tiene dos propiedades, `Name` y `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 Para obtener más información sobre el código creado por el compilador para un tipo anónimo, vea [definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
> El nombre del tipo anónimo es generado por el compilador y puede variar de la compilación a la compilación. El código no debe utilizar o confiar en el nombre de un tipo anónimo porque el nombre puede cambiar cuando se vuelve a compilar un proyecto.  
  
## <a name="declaring-an-anonymous-type"></a>Declarar un tipo anónimo  
 La declaración de una instancia de un tipo anónimo usa una lista de inicializadores para especificar las propiedades del tipo. Solo se pueden especificar propiedades cuando se declara un tipo anónimo, no otros elementos de clase, como métodos o eventos. En el ejemplo siguiente, `product1` es una instancia de un tipo anónimo que tiene dos propiedades: `Name` y `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 Si designa propiedades como propiedades clave, puede utilizarlas para comparar la igualdad de dos instancias de tipo anónimo. Sin embargo, no se pueden cambiar los valores de las propiedades de clave. Vea la sección Propiedades de clave más adelante en este tema para obtener más información.  
  
 Observe que declarar una instancia de un tipo anónimo es como declarar una instancia de un tipo con nombre mediante un inicializador de objeto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 Para obtener más información sobre otras formas de especificar propiedades de tipo anónimo, vea [Cómo: inferir nombres y tipos de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades clave difieren de las propiedades que no son de clave de varias maneras fundamentales:  
  
- Solo se comparan los valores de las propiedades de clave para determinar si dos instancias son iguales.  
  
- Los valores de las propiedades de clave son de solo lectura y no se pueden cambiar.  
  
- Solo los valores de propiedad clave se incluyen en el algoritmo de código hash generado por el compilador para un tipo anónimo.  
  
### <a name="equality"></a>Igualdad  
 Las instancias de tipos anónimos solo pueden ser iguales si son instancias del mismo tipo anónimo. El compilador trata dos instancias como instancias del mismo tipo si cumplen las condiciones siguientes:  
  
- Se declaran en el mismo ensamblado.  
  
- Sus propiedades tienen los mismos nombres, los mismos tipos deducidos y se declaran en el mismo orden. Las comparaciones de nombres no distinguen mayúsculas de minúsculas.  
  
- Las mismas propiedades de cada se marcan como propiedades de clave.  
  
- Al menos una propiedad de cada declaración es una propiedad de clave.  
  
 Una instancia de tipos anónimos que no tiene propiedades de clave es igual a sí misma.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 Dos instancias del mismo tipo anónimo son iguales si los valores de sus propiedades de clave son iguales. En los siguientes ejemplos se muestra cómo se prueba la igualdad.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>Valores de solo lectura  
 No se pueden cambiar los valores de las propiedades de clave. Por ejemplo, en `prod8` en el ejemplo anterior, los campos `Name` y `Price` se `read-only`, pero `OnHand` se puede cambiar.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Tipos anónimos de expresiones de consulta  
 Las expresiones de consulta no siempre requieren la creación de tipos anónimos. Siempre que sea posible, usan un tipo existente para contener los datos de la columna. Esto sucede cuando la consulta devuelve registros completos del origen de datos o solo un campo de cada registro. En los siguientes ejemplos de código, `customers` es una colección de objetos de una clase `Customer`. La clase tiene muchas propiedades, y puede incluir una o más en el resultado de la consulta, en cualquier orden. En los dos primeros ejemplos, no se requieren tipos anónimos porque las consultas seleccionan elementos de tipos con nombre:  
  
- `custs1` contiene una colección de cadenas, porque `cust.Name` es una cadena.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
- `custs2` contiene una colección de objetos `Customer`, porque cada elemento de `customers` es un objeto `Customer` y la consulta selecciona todo el elemento.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 Sin embargo, los tipos con nombre adecuados no siempre están disponibles. Es posible que desee seleccionar nombres y direcciones de clientes para un propósito, números de ID. de cliente y ubicaciones para otro, y nombres de cliente, direcciones y historiales de pedidos para un tercer. Los tipos anónimos le permiten seleccionar cualquier combinación de propiedades, en cualquier orden, sin declarar primero un nuevo tipo con nombre para contener el resultado. En su lugar, el compilador crea un tipo anónimo para cada compilación de propiedades. La siguiente consulta selecciona solo el nombre del cliente y el número de identificador de cada objeto de `Customer` en `customers`. Por consiguiente, el compilador crea un tipo anónimo que solo contiene esas dos propiedades.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 Tanto los nombres como los tipos de datos de las propiedades del tipo anónimo se toman de los argumentos para `Select`, `cust.Name` y `cust.ID`. Las propiedades de un tipo anónimo creado por una consulta son siempre propiedades clave. Cuando se ejecuta `custs3` en el siguiente bucle de `For Each`, el resultado es una colección de instancias de un tipo anónimo con dos propiedades de clave, `Name` y `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 Los elementos de la colección representada por `custs3` están fuertemente tipados y puede usar IntelliSense para navegar por las propiedades disponibles y comprobar sus tipos.  
  
 Para obtener más información, vea [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Decidir si usar tipos anónimos  
 Antes de crear un objeto como una instancia de una clase anónima, tenga en cuenta si es la mejor opción. Por ejemplo, si desea crear un objeto temporal que contenga datos relacionados y no necesita otros campos y métodos que pueda contener una clase completa, un tipo anónimo es una buena solución. Los tipos anónimos también son útiles si desea una selección diferente de las propiedades de cada declaración, o si desea cambiar el orden de las propiedades. Sin embargo, si el proyecto incluye varios objetos que tienen las mismas propiedades, en un orden fijo, puede declararlos más fácilmente utilizando un tipo con nombre con un constructor de clase. Por ejemplo, con un constructor adecuado, es más fácil declarar varias instancias de una clase `Product` que declarar varias instancias de un tipo anónimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 Otra ventaja de los tipos con nombre es que el compilador puede detectar un error de escritura accidental de un nombre de propiedad. En los ejemplos anteriores, `firstProd2`, `secondProd2`y `thirdProd2` están diseñados para ser instancias del mismo tipo anónimo. Sin embargo, si declarara accidentalmente `thirdProd2` de una de las siguientes maneras, su tipo sería diferente del de `firstProd2` y `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 Lo que es más importante, existen limitaciones en el uso de tipos anónimos que no se aplican a las instancias de tipos con nombre. `firstProd2`, `secondProd2`y `thirdProd2` son instancias del mismo tipo anónimo. Sin embargo, el nombre del tipo anónimo compartido no está disponible y no puede aparecer donde se espera un nombre de tipo en el código. Por ejemplo, un tipo anónimo no se puede usar para definir una firma de método, para declarar otra variable o campo, o en cualquier declaración de tipo. Como resultado, los tipos anónimos no son adecuados cuando es necesario compartir información entre métodos.  
  
## <a name="an-anonymous-type-definition"></a>Una definición de tipo anónimo  
 En respuesta a la declaración de una instancia de un tipo anónimo, el compilador crea una nueva definición de clase que contiene las propiedades especificadas.  
  
 Si el tipo anónimo contiene al menos una propiedad de clave, la definición invalida tres miembros heredados de <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>y <xref:System.Object.ToString%2A>. El código generado para probar la igualdad y determinar el valor del código hash solo tiene en cuenta las propiedades clave. Si el tipo anónimo no contiene propiedades de clave, solo se invalida <xref:System.Object.ToString%2A>. Las propiedades con nombre explícito de un tipo anónimo no pueden entrar en conflicto con estos métodos generados. Es decir, no puede usar `.Equals`, `.GetHashCode`o `.ToString` para asignar un nombre a una propiedad.  
  
 Las definiciones de tipos anónimos que tienen al menos una propiedad de clave también implementan la interfaz <xref:System.IEquatable%601?displayProperty=nameWithType>, donde `T` es el tipo del tipo anónimo.  
  
 Para obtener más información sobre el código creado por el compilador y la funcionalidad de los métodos invalidados, vea [definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Definición de tipo anónimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
