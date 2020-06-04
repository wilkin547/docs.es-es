---
title: Instrucciones
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
ms.openlocfilehash: 09fe53f4bc2b6d025b762c6595c5337263456bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401984"
---
# <a name="statements-in-visual-basic"></a>Instrucciones en Visual Basic

Una instrucción en Visual Basic es una instrucción completa. Puede contener palabras clave, operadores, variables, constantes y expresiones. Cada instrucción pertenece a una de las siguientes categorías:

- **Instrucciones de declaración**, que denominan una variable, una constante o un procedimiento, y también pueden especificar un tipo de datos.

- **Instrucciones ejecutables**, que inician acciones. Estas instrucciones pueden llamar a un método o una función, y pueden recorrer en bucle o bifurcar a través de bloques de código. Las instrucciones ejecutables incluyen **instrucciones de asignación**, que asignan un valor o una expresión a una variable o constante.

En este tema se describe cada categoría. Además, en este tema se describe cómo combinar varias instrucciones en una sola línea y cómo continuar una instrucción en varias líneas.

## <a name="declaration-statements"></a>Instrucciones de declaración

Las instrucciones de declaración se usan para asignar un nombre y definir procedimientos, variables, propiedades, matrices y constantes. Al declarar un elemento de programación, también puede definir su tipo de datos, el nivel de acceso y el ámbito. Para obtener más información, vea características de los [elementos declarados](./declared-elements/declared-element-characteristics.md).

El ejemplo siguiente contiene tres declaraciones.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

La primera declaración es la `Sub` instrucción. Junto con su `End Sub` instrucción correspondiente, declara un procedimiento denominado `applyFormat` . También especifica que `applyFormat` es `Public` , lo que significa que cualquier código que pueda hacer referencia a él puede llamarlo.

La segunda declaración es la `Const` instrucción, que declara la constante `limit` , especificando el `Integer` tipo de datos y un valor de 33.

La tercera declaración es la `Dim` instrucción, que declara la variable `thisWidget` . El tipo de datos es un objeto específico, es decir, un objeto creado a partir de la `Widget` clase. Puede declarar una variable para que sea de cualquier tipo de datos elemental o de cualquier tipo de objeto que se exponga en la aplicación que está usando.

### <a name="initial-values"></a>Valores iniciales

Cuando se ejecuta el código que contiene una instrucción de declaración, Visual Basic reserva la memoria necesaria para el elemento declarado. Si el elemento contiene un valor, Visual Basic lo inicializa en el valor predeterminado para su tipo de datos. Para obtener más información, vea el tema sobre el comportamiento en la [instrucción Dim](../../language-reference/statements/dim-statement.md).

Puede asignar un valor inicial a una variable como parte de su declaración, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Si una variable es una variable de objeto, puede crear explícitamente una instancia de su clase cuando la declare mediante la palabra clave [New Operator](../../language-reference/operators/new-operator.md) , como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Tenga en cuenta que el valor inicial especificado en una instrucción de declaración no se asigna a una variable hasta que la ejecución llega a su instrucción de declaración. Hasta ese momento, la variable contiene el valor predeterminado para su tipo de datos.

## <a name="executable-statements"></a>Instrucciones ejecutables

Una instrucción ejecutable realiza una acción. Puede llamar a un procedimiento, bifurcar a otro lugar del código, recorrer varias instrucciones o evaluar una expresión. Una instrucción de asignación es un caso especial de una instrucción ejecutable.

En el ejemplo siguiente se usa una `If...Then...Else` estructura de control para ejecutar diferentes bloques de código basándose en el valor de una variable. Dentro de cada bloque de código, un `For...Next` bucle se ejecuta un número especificado de veces.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

La `If` instrucción del ejemplo anterior comprueba el valor del parámetro `clockwise` . Si el valor es `True` , llama al `spinClockwise` método de `aWidget` . Si el valor es `False` , llama al `spinCounterClockwise` método de `aWidget` . La `If...Then...Else` estructura de control termina con `End If` .

El `For...Next` bucle dentro de cada bloque llama al método adecuado un número de veces igual al valor del `revolutions` parámetro.

## <a name="assignment-statements"></a>Instrucciones de asignación

Las instrucciones de asignación llevan a cabo operaciones de asignación, que consisten en tomar el valor del lado derecho del operador de asignación ( `=` ) y almacenarlo en el elemento de la izquierda, como en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

En el ejemplo anterior, la instrucción de asignación almacena el valor literal 42 en la variable `v` .

### <a name="eligible-programming-elements"></a>Elementos de programación válidos

El elemento de programación del lado izquierdo del operador de asignación debe ser capaz de aceptar y almacenar un valor. Esto significa que debe ser una variable o propiedad que no sea de [solo lectura](../../language-reference/modifiers/readonly.md)o debe ser un elemento de matriz. En el contexto de una instrucción de asignación, este tipo de elemento a veces se denomina *lvalue*, para "valor izquierdo".

El valor del lado derecho del operador de asignación se genera mediante una expresión, que puede estar formada por cualquier combinación de literales, constantes, variables, propiedades, elementos de matriz, otras expresiones o llamadas a funciones. Esto se ilustra en el siguiente ejemplo.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

En el ejemplo anterior se agrega el valor almacenado en la variable `y` al valor contenido en la variable `z` y, a continuación, se agrega el valor devuelto por la llamada a la función `findResult` . El valor total de esta expresión se almacena en la variable `x` .

### <a name="data-types-in-assignment-statements"></a>Tipos de datos en instrucciones de asignación

Además de los valores numéricos, el operador de asignación también puede asignar `String` valores, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

También puede asignar `Boolean` valores, mediante un `Boolean` literal o una `Boolean` expresión, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Del mismo modo, puede asignar los valores adecuados a los elementos de programación del `Char` `Date` tipo de datos, o `Object` . También puede asignar una instancia de objeto a un elemento declarado como de la clase de la que se crea la instancia.

### <a name="compound-assignment-statements"></a>Instrucciones de asignación compuesta

Las *instrucciones de asignación compuesta* realizan primero una operación en una expresión antes de asignarla a un elemento de programación. En el siguiente ejemplo se muestra uno de estos operadores, `+=` , que incrementa el valor de la variable en el lado izquierdo del operador por el valor de la expresión de la derecha.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

En el ejemplo anterior se agrega 1 al valor de `n` y, a continuación, se almacena ese nuevo valor en `n` . Es un equivalente abreviado de la siguiente instrucción:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Se puede realizar una serie de operaciones de asignación compuesta mediante el uso de operadores de este tipo. Para obtener una lista de estos operadores y más información sobre ellos, vea [operadores de asignación](../../language-reference/operators/assignment-operators.md).

El operador de asignación de concatenación ( `&=` ) es útil para agregar una cadena al final de las cadenas ya existentes, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Conversiones de tipos en instrucciones de asignación

El valor que se asigna a una variable, una propiedad o un elemento de matriz debe ser de un tipo de datos adecuado para ese elemento de destino. En general, debe intentar generar un valor del mismo tipo de datos que el del elemento de destino. Sin embargo, algunos tipos se pueden convertir en otros tipos durante la asignación.

Para obtener información sobre cómo convertir entre tipos de datos, vea [conversiones de tipos en Visual Basic](./data-types/type-conversions.md). En Resumen, Visual Basic convierte automáticamente un valor de un tipo determinado a cualquier otro tipo al que se amplíe. Una *conversión de ampliación* es aquella en que siempre se realiza correctamente en tiempo de ejecución y no pierde ningún dato. Por ejemplo, Visual Basic convierte un `Integer` valor en `Double` cuando es adecuado, porque `Integer` se amplía a `Double` . Para obtener más información, consulta [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

Las *conversiones de restricción* (las que no son de ampliación) suponen un riesgo de error en tiempo de ejecución o de pérdida de datos. Puede realizar una conversión de restricción explícitamente mediante una función de conversión de tipos, o bien puede indicar al compilador que realice todas las conversiones implícitamente estableciendo `Option Strict Off` . Para obtener más información, vea [conversiones implícitas y explícitas](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Colocar varias instrucciones en una línea

Puede tener varias instrucciones en una sola línea separadas por el carácter de dos puntos ( `:` ). Esto se ilustra en el siguiente ejemplo.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Aunque a veces es conveniente, esta forma de sintaxis hace que el código sea difícil de leer y mantener. Por lo tanto, se recomienda mantener una instrucción en una línea.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuar una instrucción en varias líneas

Una instrucción normalmente cabe en una línea, pero cuando es demasiado larga, puede continuar en la línea siguiente con una secuencia de continuación de línea, que consta de un espacio seguido de un carácter de subrayado ( `_` ) seguido de un retorno de carro. En el ejemplo siguiente, la `MsgBox` instrucción ejecutable continúa en dos líneas.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuación de línea implícita

En muchos casos, puede continuar una instrucción en la siguiente línea consecutiva sin usar el carácter de subrayado ( `_` ). Los siguientes elementos de sintaxis continúan implícitamente la instrucción en la siguiente línea de código.

- Después de una coma ( `,` ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Después de un paréntesis de apertura ( `(` ) o antes de un paréntesis de cierre ( `)` ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Después de una llave de apertura ( `{` ) o antes de una llave de cierre ( `}` ). Por ejemplo:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Para obtener más información, vea [inicializadores de objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md) o [inicializadores de colección](./collection-initializers/index.md).

- Después de una expresión insertada abierta ( `<%=` ) o antes del cierre de una expresión incrustada ( `%>` ) dentro de un literal XML. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Para obtener más información, vea [expresiones incrustadas en XML](./xml/embedded-expressions-in-xml.md).

- Después del operador de concatenación ( `&` ). Por ejemplo:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Para obtener más información, vea [operadores enumerados por funcionalidad](../../language-reference/operators/operators-listed-by-functionality.md).

- Después de los operadores de asignación ( `=` , `&=` , `:=` , `+=` , `-=` , `*=` , `/=` , `\=` , `^=` , `<<=` , `>>=` ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Para obtener más información, vea [operadores enumerados por funcionalidad](../../language-reference/operators/operators-listed-by-functionality.md).

- Después de los operadores binarios ( `+` , `-` , `/` , `*` , `Mod` ,, `<>` `<` , `>` , `<=` , `>=` , `^` , `>>` , `<<` , `And` , `AndAlso` , `Or` , `OrElse` , `Like` , `Xor` ) dentro de una expresión. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Para obtener más información, vea [operadores enumerados por funcionalidad](../../language-reference/operators/operators-listed-by-functionality.md).

- Después de `Is` los `IsNot` operadores y. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Para obtener más información, vea [operadores enumerados por funcionalidad](../../language-reference/operators/operators-listed-by-functionality.md).

- Después de un carácter calificador de miembro ( `.` ) y antes del nombre del miembro. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Sin embargo, debe incluir un carácter de continuación de línea ( `_` ) después de un carácter calificador de miembro cuando esté usando la `With` instrucción o proporcionando valores en la lista de inicialización para un tipo. Considere la posibilidad de dividir la línea después del operador de asignación (por ejemplo, `=` ) cuando use `With` instrucciones o listas de inicialización de objetos. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Para obtener más información, vea [con... End with instrucciones](../../language-reference/statements/with-end-with-statement.md) o [inicializadores de objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Después de un calificador de propiedad de eje XML ( `.` o `.@` o `...` ). Sin embargo, debe incluir un carácter de continuación de línea ( `_` ) al especificar un calificador de miembro cuando use la `With` palabra clave. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Para obtener más información, vea [propiedades del eje XML](../../language-reference/xml-axis/index.md).

- Después de un signo menor que (<) o antes de un signo mayor que ( `>` ) cuando se especifica un atributo. También después de un signo mayor que ( `>` ) al especificar un atributo. Sin embargo, debe incluir un carácter de continuación de línea ( `_` ) al especificar atributos de nivel de ensamblado o de nivel de módulo. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Para obtener más información, vea [información general sobre atributos](../concepts/attributes/index.md).

- Operadores de consulta Before y After ( `Aggregate` , `Distinct` ,,,,,, `From` `Group By` `Group Join` `Join` `Let` `Order By` , `Select` ,,,,, `Skip` `Skip While` `Take` `Take While` `Where` , `In` , `Into` , `On` , `Ascending` y `Descending` ). No se puede dividir una línea entre las palabras clave de los operadores de consulta que se componen de varias palabras clave ( `Order By` , `Group Join` , `Take While` y `Skip While` ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Para obtener más información, vea [consultas](../../language-reference/queries/index.md).

- Después de la `In` palabra clave en una `For Each` instrucción. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Para obtener más información, vea [para cada uno... Instrucción siguiente](../../language-reference/statements/for-each-next-statement.md).

- Después de la `From` palabra clave en un inicializador de colección. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Para obtener más información, vea [Inicializadores de colección](collection-initializers/index.md).

## <a name="adding-comments"></a>Agregar comentarios

El código fuente no siempre se explica por sí mismo, incluso al programador que lo escribió. Para ayudar a documentar el código, por lo tanto, la mayoría de los programadores hacen un uso liberal de los comentarios incrustados. Los comentarios en el código pueden explicar un procedimiento o una instrucción determinada a cualquier persona que lea o trabaje con él más adelante. Visual Basic omite los comentarios durante la compilación y no afectan al código compilado.

Las líneas de comentario comienzan con un apóstrofo ( `'` ) o `REM` seguidos de un espacio. Se pueden agregar en cualquier parte del código, excepto en una cadena. Para anexar un comentario a una instrucción, inserte un apóstrofo o `REM` después de la instrucción, seguido del comentario. Los comentarios también pueden ir en una línea independiente. En el ejemplo siguiente se muestran estas posibilidades.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Comprobar errores de compilación

Si, después de escribir una línea de código, la línea se muestra con un subrayado azul ondulado (también puede aparecer un mensaje de error), se produce un error de sintaxis en la instrucción. Debe averiguar cuál es el problema con la instrucción (examinando la lista de tareas o colocando el puntero sobre el error con el puntero del mouse y leyendo el mensaje de error) y corríjalo. Hasta que haya corregido todos los errores de sintaxis en el código, el programa no se compilará correctamente.

## <a name="related-sections"></a>Secciones relacionadas

|Término|Definición|
|---|---|
|[Operadores de asignación](../../language-reference/operators/assignment-operators.md)|Proporciona vínculos a páginas de referencia del lenguaje que abarcan operadores de asignación como `=` , `*=` y `&=` .|
|[Operadores y expresiones](./operators-and-expressions/index.md)|Muestra cómo combinar elementos con operadores para producir nuevos valores.|
|[Procedimiento Interrupción y combinación de instrucciones en código](../program-structure/how-to-break-and-combine-statements-in-code.md)|Muestra cómo dividir una sola instrucción en varias líneas y cómo colocar varias instrucciones en la misma línea.|
|[Procedimiento Instrucciones de etiquetas](../program-structure/how-to-label-statements.md)|Muestra cómo etiquetar una línea de código.|
