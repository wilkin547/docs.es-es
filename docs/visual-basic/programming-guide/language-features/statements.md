---
title: Instrucciones en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506295"
---
# <a name="statements-in-visual-basic"></a>Instrucciones en Visual Basic

Una instrucción en Visual Basic es una instrucción completa. Puede contener las palabras clave, operadores, variables, constantes y expresiones. Cada instrucción pertenece a una de las siguientes categorías:

- **Las instrucciones de declaración**, que el nombre de una variable, constante o procedimiento y también puede especificar un tipo de datos.

- **Las instrucciones ejecutables**, que inician acciones. Estas instrucciones pueden llamar a un método o función, y pueden bucle o a través de bloques de código. Las instrucciones ejecutables incluyen **instrucciones de asignación**, que asignan un valor o expresión a una variable o constante.

Este tema describe cada categoría. Además, en este tema se describe cómo combinar varias instrucciones en una sola línea y continuar una instrucción en varias líneas.

## <a name="declaration-statements"></a>Instrucciones de declaración

Utilice las instrucciones de declaración para un nombre y definen procedimientos, variables, propiedades, matrices y constantes. Cuando se declara un elemento de programación, también puede definir su tipo de datos, el nivel de acceso y el ámbito. Para obtener más información, consulte [características de los elementos declarados](./declared-elements/declared-element-characteristics.md).

El ejemplo siguiente contiene tres declaraciones.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

La primera declaración es la `Sub` instrucción. Junto con su coincidencia `End Sub` instrucción, declara un procedimiento denominado `applyFormat`. También especifica que `applyFormat` es `Public`, lo que significa que cualquier código que puede hacer referencia a él puede llamarlo.

La segunda declaración es la `Const` instrucción, que declara la constante `limit`, especificando el `Integer` tipo de datos y un valor de 33.

La tercera declaración es la `Dim` instrucción, que declara la variable `thisWidget`. El tipo de datos es un objeto específico, es decir, se crea un objeto desde el `Widget` clase. Puede declarar una variable de cualquier tipo de datos básico o de cualquier tipo de objeto que se expone en la aplicación que esté utilizando.

### <a name="initial-values"></a>Valores iniciales

Cuando se ejecuta el código que contiene una instrucción de declaración, Visual Basic reserva la memoria necesaria para el elemento declarado. Si el elemento contiene un valor, en Visual Basic se inicializa en el valor predeterminado para su tipo de datos. Para obtener más información, vea "Comportamiento" en [instrucción Dim](../../language-reference/statements/dim-statement.md).

Puede asignar un valor inicial a una variable como parte de su declaración, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Si una variable es una variable de objeto, puede crear una instancia de su clase explícitamente cuando se declara mediante el uso de la [nuevo operador](../../../visual-basic/language-reference/operators/new-operator.md) palabra clave, como en el ejemplo siguiente se muestra.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Tenga en cuenta que el valor inicial especificado en una instrucción de declaración no está asignado a una variable hasta que la ejecución llega a su instrucción de declaración. Hasta ese momento, la variable contiene el valor predeterminado de su tipo de datos.

## <a name="executable-statements"></a>Instrucciones ejecutables

Una instrucción ejecutable realiza una acción. Puede llamar a un procedimiento, bifurcar hacia otro lugar en el código, recorrer varias instrucciones, o evalúa una expresión. Una instrucción de asignación es un caso especial de una instrucción ejecutable.

En el ejemplo siguiente se usa un `If...Then...Else` estructura para ejecutar distintos bloques de código en función del valor de una variable de control. Dentro de cada bloque de código, un `For...Next` un número especificado de veces que ejecuta el bucle.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

El `If` instrucción en el ejemplo anterior comprueba el valor del parámetro `clockwise`. Si el valor es `True`, llama a la `spinClockwise` método `aWidget`. Si el valor es `False`, llama a la `spinCounterClockwise` método `aWidget`. El `If...Then...Else` estructura de control finaliza con `End If`.

El `For...Next` bucle dentro de cada bloque llama al método adecuado un número de veces igual al valor de la `revolutions` parámetro.

## <a name="assignment-statements"></a>Instrucciones de asignación

Instrucciones de asignación llevan a cabo las operaciones de asignación, que constan de tomar el valor en el lado derecho del operador de asignación (`=`) y lo almacena en el elemento de la izquierda, como en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

En el ejemplo anterior, la instrucción de asignación almacena el valor literal 42 en la variable `v`.

### <a name="eligible-programming-elements"></a>Elementos de programación elegibles

El elemento de programación en el lado izquierdo del operador de asignación debe ser capaz de Aceptar y almacenar un valor. Esto significa que debe ser una variable o propiedad que no sea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), o debe ser un elemento de matriz. En el contexto de una instrucción de asignación, ese elemento a veces se denomina un *lvalue*, "valor izquierdo".

El valor en el lado derecho del operador de asignación es generado por una expresión, que puede constar de cualquier combinación de literales, constantes, variables, propiedades, elementos de matriz, otras expresiones o llamadas de función. Esto se ilustra en el siguiente ejemplo:

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

El ejemplo anterior agrega el valor almacenado en la variable `y` al valor almacenado en la variable `z`y, a continuación, agrega el valor devuelto por la llamada a función `findResult`. El valor total de esta expresión, a continuación, se almacena en la variable `x`.

### <a name="data-types-in-assignment-statements"></a>Tipos de datos en instrucciones de asignación

Además de los valores numéricos, el operador de asignación también puede asignar `String` valores, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

También puede asignar `Boolean` valores, ya sea mediante un `Boolean` literal o un `Boolean` expresión, como en el ejemplo siguiente se muestra.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

De forma similar, puede asignar los valores adecuados para los elementos de programación de la `Char`, `Date`, o `Object` tipo de datos. También puede asignar una instancia de objeto a un elemento que se declara de la clase desde el que se creó esa instancia.

### <a name="compound-assignment-statements"></a>Instrucciones de asignación compuesta

*Instrucciones de asignación compuesta* realizar primero una operación en una expresión antes de asignarlo a un elemento de programación. El ejemplo siguiente muestra uno de estos operadores, `+=`, lo que incrementa el valor de la variable en el lado izquierdo del operador en el valor de la expresión de la derecha.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

El ejemplo anterior suma 1 al valor de `n`y, a continuación, almacena ese valor nuevo en `n`. Una forma abreviada es equivalente a la siguiente instrucción:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Una serie de operaciones de asignación compuesta se puede realizar con los operadores de este tipo. Para obtener una lista de estos operadores y más información sobre ellos, consulte [operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md).

El operador de asignación de concatenación (`&=`) es útil para agregar una cadena al final de ya existente de cadenas, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Conversiones de tipos en instrucciones de asignación

El valor que se asigna a una variable, una propiedad o un elemento de matriz debe ser de un tipo de datos apropiado para ese elemento de destino. En general, debería intentar generar un valor del mismo tipo de datos que el del elemento de destino. Sin embargo, algunos tipos se pueden convertir a otros tipos durante la asignación.

Para obtener información sobre cómo convertir entre tipos de datos, vea [las conversiones de tipos en Visual Basic](./data-types/type-conversions.md). En resumen, Visual Basic convierte automáticamente un valor de un tipo determinado en cualquier otro tipo al que se amplía. Un *una conversión de ampliación* es aquella que siempre se realiza correctamente en tiempo de ejecución y no perderá ningún dato. Por ejemplo, Visual Basic convierte un `Integer` valor `Double` cuando sea apropiado, dado que `Integer` se amplía a `Double`. Para obtener más información, consulta [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Las conversiones de restricción* (aquellos que no son de ampliación) llevan un riesgo de error en tiempo de ejecución o de pérdida de datos. Puede realizar una conversión de restricción explícitamente mediante el uso de una función de conversión de tipo, o se puede indicar al compilador que realice todas las conversiones implícitamente estableciendo `Option Strict Off`. Para obtener más información, consulte [conversiones implícitas y explícitas](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Colocar varias instrucciones en una sola línea

Puede tener varias instrucciones en una sola línea, separada por dos puntos (`:`) caracteres. Esto se ilustra en el siguiente ejemplo:

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Aunque resulta útil en ocasiones, esta forma de sintaxis hace que su código difícil de leer y mantener. Por lo tanto, se recomienda que mantenga una instrucción en una línea.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuar una instrucción en varias líneas

Una instrucción que normalmente se ajusta en una sola línea, pero cuando es demasiado largo, puede continuar en la siguiente línea mediante una secuencia de continuación de línea, que consta de un espacio seguido por un carácter de subrayado (`_`) seguido por un retorno de carro. En el ejemplo siguiente, la `MsgBox` instrucción ejecutable continúa en dos líneas.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuación de línea implícita

En muchos casos, puede continuar una instrucción en la siguiente línea consecutiva sin usar el carácter de subrayado (`_`). Los siguientes elementos de sintaxis continúan implícitamente la instrucción en la siguiente línea de código.

- Después de una coma (`,`). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Después de un paréntesis de apertura (`(`) o antes de un paréntesis de cierre (`)`). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Después de una llave de apertura (`{`) o antes de una llave de cierre (`}`). Por ejemplo:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md) o [inicializadores de colección](./collection-initializers/index.md).

- Después de una abierta expresión incrustada (`<%=`) o antes del cierre de una expresión incrustada (`%>`) dentro de un literal XML. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Para obtener más información, consulte [expresiones incrustadas en XML](./xml/embedded-expressions-in-xml.md).

- Después del operador de concatenación (`&`). Por ejemplo:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de operadores de asignación (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de operadores binarios (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) dentro de una expresión. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de la `Is` y `IsNot` operadores. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de un carácter calificador de miembro (`.`) y delante del nombre del miembro. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Sin embargo, debe incluir un carácter de continuación de línea (`_`) siguiendo un carácter calificador de miembro cuando se usa el `With` instrucción o proporcionando valores en la lista de inicialización para un tipo. Considere la posibilidad de interrumpir la línea después del operador de asignación (por ejemplo, `=`) cuando se utiliza `With` instrucciones o listas de inicialización de objetos. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Para obtener más información, consulte [con... Terminar con la instrucción](../../../visual-basic/language-reference/statements/with-end-with-statement.md) o [inicializadores de objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Después de un calificador de propiedad de eje XML (`.` o `.@` o `...`). Sin embargo, debe incluir un carácter de continuación de línea (`_`) al especificar un calificador de miembro cuando se usa el `With` palabra clave. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Para obtener más información, consulte [propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/index.md).

- Después de una menor-que el inicio de sesión (<) o antes de una mayor-que el inicio de sesión (`>`) cuando se especifica un atributo. También después de una mayor-que el inicio de sesión (`>`) cuando se especifica un atributo. Sin embargo, debe incluir un carácter de continuación de línea (`_`) al especificar atributos de nivel de ensamblado o el nivel de módulo. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Para obtener más información, consulte [información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Antes y después de operadores de consulta (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, y `Descending`). No se puede interrumpir una línea entre las palabras clave de operadores de consulta que se componen de varias palabras clave (`Order By`, `Group Join`, `Take While`, y `Skip While`). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Para obtener más información, consulte [consultas](../../../visual-basic/language-reference/queries/index.md).

- Después de la `In` palabra clave en un `For Each` instrucción. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Para obtener más información, consulte [For Each... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Después de la `From` palabra clave en un inicializador de colección. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Agregar comentarios

Código fuente no siempre es fácil de entender, incluso para los programadores que lo escribieron. Para ayudar a documentar su código, por lo tanto, la mayoría de los programadores utilizan libremente comentarios incrustados. Comentarios en el código pueden explicar un procedimiento o una instrucción concreta a cualquiera que lea o trabajar con ella más adelante. Visual Basic omite los comentarios durante la compilación y no afectan el código compilado.

Líneas de comentario comienzan con un apóstrofe (`'`) o `REM` seguida por un espacio. Se pueden agregar en cualquier lugar en el código, excepto dentro de una cadena. Para anexar un comentario a una instrucción, inserte un apóstrofo o `REM` después de la instrucción, seguida del comentario. Los comentarios también pueden ir en su propia línea independiente. El ejemplo siguiente muestra estas posibilidades.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Comprobar si hay errores de compilación

Si, después de escribir una línea de código, se muestra la línea con un subrayado ondulado de color azul (también puede aparecer un mensaje de error), hay un error de sintaxis en la instrucción. Debe saber cuál es el problema con la instrucción (mediante la búsqueda en la lista de tareas, o el mouse sobre el error con el puntero del mouse y leer el mensaje de error) y corregirlo. Hasta que haya solucionado todos los errores de sintaxis en el código, se producirá un error en el programa para compilarse correctamente.

## <a name="related-sections"></a>Secciones relacionadas

|Término|de esquema JSON|
|---|---|
|[Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)|Proporciona vínculos a páginas de referencia del lenguaje que describen los operadores de asignación como `=`, `*=`, y `&=`.|
|[Operadores y expresiones](./operators-and-expressions/index.md)|Se muestra cómo combinar elementos con operadores para obtener nuevos valores.|
|[Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Muestra cómo dividir una única instrucción en varias líneas y cómo colocar varias instrucciones en la misma línea.|
|[Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Muestra cómo etiquetar una línea de código.|
