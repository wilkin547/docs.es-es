---
title: 'Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 612b1dcea0f776dfd4580803e76f2785e7d28da6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930595"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inicializadores de objeto: Tipos con nombre y anónimos (Visual Basic)
Los inicializadores de objeto permiten especificar las propiedades de un objeto complejo mediante el uso de una sola expresión. Se puede usar para crear instancias de tipos con nombre y de tipos anónimos.  
  
## <a name="declarations"></a>Declaraciones  
 Las declaraciones de las instancias de tipos con nombre y anónimos pueden parecer casi idénticas, pero sus efectos no son iguales. Cada categoría tiene funcionalidades y restricciones de su propio. El ejemplo siguiente muestra una manera cómoda de declarar e inicializar una instancia de una clase con nombre, `Customer`, mediante el uso de una lista de inicializadores de objeto. Tenga en cuenta que se especifica el nombre de la clase después de la palabra clave `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Un tipo anónimo no tiene ningún nombre utilizable. Por lo tanto, una instancia de un tipo anónimo no puede incluir un nombre de clase.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 Los requisitos y los resultados de las dos declaraciones no son los mismos. Para `namedCust`, un `Customer` clase que tiene un `Name` propiedad ya debe existir y la declaración crea una instancia de esa clase. Para `anonymousCust`, el compilador define una nueva clase que tiene una propiedad, una cadena denominada `Name`y crea una nueva instancia de esa clase.  
  
## <a name="named-types"></a>Tipos con nombre  
 Los inicializadores de objeto proporcionan una manera sencilla de llamar al constructor de un tipo y, a continuación, establezca los valores de algunas o todas las propiedades en una sola instrucción. El compilador invoca al constructor adecuado para la instrucción: el constructor predeterminado si no hay argumentos o un constructor con parámetros si se envían uno o más argumentos. Después de eso, se inicializan las propiedades especificadas en el orden en que se presentan en la lista de inicializadores.  
  
 Cada inicialización de la lista de inicializadores consta de la asignación de un valor inicial a un miembro de la clase. Los nombres y tipos de datos de los miembros se determinan cuando se define la clase. En los ejemplos siguientes, el `Customer` clase debe existir y deben tienen miembros con nombre `Name` y `City` que puede aceptar los valores de cadena.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 Como alternativa, puede obtener el mismo resultado utilizando el código siguiente:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Cada una de estas declaraciones es equivalente al ejemplo siguiente se crea un `Customer` objeto utilizando el constructor predeterminado y, a continuación, especifica los valores iniciales de la `Name` y `City` propiedades mediante el uso de un `With` instrucción.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Si el `Customer` clase contiene un constructor con parámetros que le permite enviar un valor para `Name`, por ejemplo, también puede declarar e inicializar un `Customer` objeto de las maneras siguientes:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 No es necesario inicializar todas las propiedades, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Sin embargo, la lista de inicialización no puede estar vacía. Las propiedades sin inicializar conservan sus valores predeterminados.  
  
### <a name="type-inference-with-named-types"></a>Inferencia de tipos con tipos con nombre  
 Puede reducir el código para la declaración de `cust1` combinando los inicializadores de objeto y la inferencia de tipo local. Esto le permite omitir la `As` cláusula en la declaración de variable. El tipo de datos de la variable se deduce del tipo del objeto que se crea mediante la asignación. En el ejemplo siguiente, el tipo de `cust6` es `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Comentarios acerca de los tipos con nombre  
  
-   Un miembro de clase no se puede inicializar más de una vez en la lista de inicializadores de objeto. La declaración de `cust7` produce un error.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Un miembro puede utilizarse para inicializar u otro campo. Si se tiene acceso a un miembro antes de que se ha inicializado, como se muestra en la siguiente declaración de `cust8`, se usará el valor predeterminado. Recuerde que cuando se procesa una declaración que usa a un inicializador de objeto, lo primero que ocurre es que se invoca al constructor apropiado. Después de eso, se inicializan los campos individuales de la lista de inicializadores. En los ejemplos siguientes, el valor predeterminado para `Name` se asigna para `cust8`, y se asigna un valor inicializado en `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     En el ejemplo siguiente se usa el constructor parametrizado de `cust3` y `cust4` para declarar e inicializar `cust10` y `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Se pueden anidar inicializadores de objeto. En el ejemplo siguiente, `AddressClass` es una clase que tiene dos propiedades, `City` y `State`y el `Customer` clase tiene un `Address` propiedad que es una instancia de `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   La lista de inicialización no puede estar vacía.  
  
-   La instancia que se está inicializarla no puede ser de tipo Object.  
  
-   No pueden ser miembros de clase que se inicializan los miembros compartidos, miembros de solo lectura, constantes o llamadas a métodos.  
  
-   Los miembros de clase que se está inicializando no indexados o calificados. Los ejemplos siguientes provocan errores del compilador:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipos anónimos  
 Tipos anónimos usan a inicializadores de objeto para crear instancias de tipos nuevos que no se define explícitamente y el nombre. En su lugar, el compilador genera un tipo según las propiedades designadas en la lista de inicializadores de objeto. Dado que no se especifica el nombre del tipo, se conoce como un *tipo anónimo*. Por ejemplo, compare la declaración siguiente a la anterior para `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 Sintácticamente, la única diferencia es que se especifica ningún nombre después de `New` para el tipo de datos. Sin embargo, lo que sucede es bastante diferente. El compilador define un nuevo tipo anónimo que tiene dos propiedades, `Name` y `City`y crea una instancia de él con los valores especificados. Inferencia de tipo determina los tipos de `Name` y `City` en el ejemplo de cadenas.  
  
> [!CAUTION]
>  El nombre del tipo anónimo es generado por el compilador y puede variar de una compilación a otra. El código no debe utilizar o se basan en el nombre de un tipo anónimo.  
  
 Dado que el nombre del tipo no está disponible, no puede usar un `As` cláusula para declarar `cust13`. Debe deducir su tipo. No se usa el enlace en tiempo de ejecución, esto limita el uso de tipos anónimos a las variables locales.  
  
 Tipos anónimos ofrecen una compatibilidad fundamental para [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consultas. Para obtener más información sobre el uso de tipos anónimos en las consultas, vea [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) y [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Comentarios sobre los tipos anónimos  
  
-   Normalmente, todos o la mayoría de las propiedades de una declaración de tipos anónimos serán propiedades de clave, que se indican escribiendo la palabra clave `Key` delante del nombre de propiedad.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Para obtener más información acerca de las propiedades de clave, consulte [clave](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Llamada como tipos, las listas de inicializadores para las definiciones de tipo anónimo deben declarar al menos una propiedad.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Cuando se declara una instancia de un tipo anónimo, el compilador genera una definición de tipo anónimo coincidente. Los nombres y tipos de datos de las propiedades se toman de la declaración de instancia y se incluyen el compilador en la definición. Las propiedades no son denominadas y definidas con antelación, como se haría para un tipo con nombre. Se deducen sus tipos. No se puede especificar los tipos de datos de las propiedades mediante el uso de un `As` cláusula.  
  
-   Tipos anónimos también pueden establecer los nombres y valores de sus propiedades de otras maneras. Por ejemplo, una propiedad de tipo anónimo puede tomar el nombre y el valor de una variable, o el nombre y valor de una propiedad de otro objeto.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Para obtener más información sobre las opciones para definir las propiedades en tipos anónimos, consulte [Cómo: deducir los nombres de propiedad y los tipos en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Vea también  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)  
 [Declarar un objeto usando un inicializador de objeto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
