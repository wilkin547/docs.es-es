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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401470"
---
# <a name="statements-in-visual-basic"></a>Instrucciones en Visual Basic

Una instrucción en Visual Basic es una instrucción completa. Puede contener palabras clave, operadores, variables, constantes y expresiones. Cada instrucción pertenece a una de las siguientes categorías:

- **Declaraciones**, que nombran una variable, constante o procedimiento, y también pueden especificar un tipo de datos.

- **Executable Statements**, que inician acciones. Estas instrucciones pueden llamar a un método o función, y pueden recorrer en bucle o bifurcar a través de bloques de código. Las instrucciones ejecutables incluyen **instrucciones de asignación**, que asignan un valor o una expresión a una variable o constante.

En este tema se describe cada categoría. Además, en este tema se describe cómo combinar varias instrucciones en una sola línea y cómo continuar una instrucción en varias líneas.

## <a name="declaration-statements"></a>Instrucciones de declaración

Las instrucciones de declaración se utilizan para asignar un nombre y definir procedimientos, variables, propiedades, matrices y constantes. Al declarar un elemento de programación, también puede definir su tipo de datos, nivel de acceso y ámbito. Para obtener más información, vea [Características de elementos declarados](./declared-elements/declared-element-characteristics.md).

El ejemplo siguiente contiene tres declaraciones.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

La primera declaración es la `Sub` declaración. Junto con `End Sub` su instrucción coincidente, `applyFormat`declara un procedimiento denominado . También especifica que `applyFormat` `Public`es , lo que significa que cualquier código que puede hacer referencia a él puede llamarlo.

La segunda declaración es la `Const` instrucción, que declara la constante, `limit`especificando el `Integer` tipo de datos y un valor de 33.

La tercera declaración es la `Dim` instrucción, que declara la variable `thisWidget`. El tipo de datos es un objeto específico, es decir, un objeto creado a partir de la `Widget` clase. Puede declarar una variable para que sea de cualquier tipo de datos elemental o de cualquier tipo de objeto que se expone en la aplicación que está utilizando.

### <a name="initial-values"></a>Valores iniciales

Cuando se ejecuta el código que contiene una instrucción de declaración, Visual Basic reserva la memoria necesaria para el elemento declarado. Si el elemento contiene un valor, Visual Basic lo inicializa en el valor predeterminado para su tipo de datos. Para obtener más información, consulte "Comportamiento" en [Dim (instrucción).](../../language-reference/statements/dim-statement.md)

Puede asignar un valor inicial a una variable como parte de su declaración, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

Si una variable es una variable de objeto, puede crear explícitamente una instancia de su clase cuando la declare mediante la palabra clave [New Operator,](../../../visual-basic/language-reference/operators/new-operator.md) como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

Tenga en cuenta que el valor inicial que especifique en una instrucción de declaración no se asigna a una variable hasta que la ejecución alcanza su instrucción de declaración. Hasta ese momento, la variable contiene el valor predeterminado para su tipo de datos.

## <a name="executable-statements"></a>Declaraciones ejecutables

Una instrucción ejecutable realiza una acción. Puede llamar a un procedimiento, bifurcara a otro lugar del código, recorrer varias instrucciones o evaluar una expresión. Una instrucción de asignación es un caso especial de una instrucción ejecutable.

En el ejemplo `If...Then...Else` siguiente se utiliza una estructura de control para ejecutar diferentes bloques de código en función del valor de una variable. Dentro de cada bloque `For...Next` de código, un bucle ejecuta un número especificado de veces.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

La `If` instrucción del ejemplo anterior comprueba el `clockwise`valor del parámetro . Si el `True`valor es `spinClockwise` , `aWidget`llama al método de . Si el `False`valor es `spinCounterClockwise` , `aWidget`llama al método de . La `If...Then...Else` estructura de `End If`control termina con .

El `For...Next` bucle dentro de cada bloque llama al método adecuado `revolutions` un número de veces igual al valor del parámetro.

## <a name="assignment-statements"></a>Declaraciones de asignación

Las instrucciones de asignación llevan a cabo operaciones de asignación,`=`que consisten en tomar el valor en el lado derecho del operador de asignación ( ) y almacenarlo en el elemento de la izquierda, como en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

En el ejemplo anterior, la instrucción de asignación `v`almacena el valor literal 42 en la variable .

### <a name="eligible-programming-elements"></a>Elementos de programación elegibles

El elemento de programación en el lado izquierdo del operador de asignación debe ser capaz de aceptar y almacenar un valor. Esto significa que debe ser una variable o propiedad que no sea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), o debe ser un elemento de matriz. En el contexto de una instrucción de asignación, un elemento de este tipo a veces se denomina *lvalue*, para "valor izquierdo."

El valor en el lado derecho del operador de asignación se genera mediante una expresión, que puede constar de cualquier combinación de literales, constantes, variables, propiedades, elementos de matriz, otras expresiones o llamadas de función. Esto se ilustra en el siguiente ejemplo.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

En el ejemplo anterior se agrega `y` el valor mantenido `z`en variable al valor mantenido en `findResult`variable y, a continuación, se agrega el valor devuelto por la llamada a la función . A continuación, el valor total `x`de esta expresión se almacena en variable .

### <a name="data-types-in-assignment-statements"></a>Tipos de datos en extractos de asignación

Además de los valores numéricos, el operador de asignación también puede asignar `String` valores, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

También puede `Boolean` asignar valores, `Boolean` mediante un `Boolean` literal o una expresión, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

Del mismo modo, puede asignar valores `Char` `Date`adecuados `Object` a los elementos de programación del tipo de datos , , o . También puede asignar una instancia de objeto a un elemento declarado como de la clase desde la que se crea esa instancia.

### <a name="compound-assignment-statements"></a>Declaraciones de asignación compuesta

Las instrucciones de *asignación compuesta realizan* primero una operación en una expresión antes de asignarla a un elemento de programación. En el ejemplo siguiente se `+=`muestra uno de estos operadores, , que incrementa el valor de la variable en el lado izquierdo del operador por el valor de la expresión de la derecha.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

En el ejemplo anterior se agrega `n`1 al valor de `n`, y, a continuación, almacena ese nuevo valor en . Es un equivalente abreviado de la siguiente declaración:

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

Se puede realizar una variedad de operaciones de asignación de compuestos utilizando operadores de este tipo. Para obtener una lista de estos operadores y más información sobre ellos, consulte Operadores de [asignación](../../../visual-basic/language-reference/operators/assignment-operators.md).

El operador de`&=`asignación de concatenación ( ) es útil para agregar una cadena al final de cadenas ya existentes, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>Escriba Conversiones en extractos de asignación

El valor que asigne a una variable, propiedad o elemento de matriz debe ser de un tipo de datos adecuado para ese elemento de destino. En general, debe intentar generar un valor del mismo tipo de datos que el del elemento de destino. Sin embargo, algunos tipos se pueden convertir a otros tipos durante la asignación.

Para obtener información sobre la conversión entre tipos de datos, vea [Conversiones](./data-types/type-conversions.md)de tipos en Visual Basic . En resumen, Visual Basic convierte automáticamente un valor de un tipo determinado a cualquier otro tipo al que se amplía. Una *conversión de ampliación* es una que siempre se realiza correctamente en tiempo de ejecución y no pierde ningún dato. Por ejemplo, Visual Basic `Integer` convierte `Double` un valor `Integer` en cuando `Double`sea apropiado, porque se amplía a . Para obtener más información, consulta [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).

*Las conversiones* de restricción (aquellas que no se están ampliando) conllevan un riesgo de error en tiempo de ejecución o de pérdida de datos. Puede realizar una conversión de restricción explícitamente mediante una función de conversión de `Option Strict Off`tipos, o puede indicar al compilador que realice todas las conversiones implícitamente estableciendo . Para obtener más información, vea [Conversiones implícitas y explícitas](./data-types/implicit-and-explicit-conversions.md).

## <a name="putting-multiple-statements-on-one-line"></a>Poner varias declaraciones en una línea

Puede tener varias instrucciones en una sola línea`:`separadas por el carácter de dos puntos ( ). Esto se ilustra en el siguiente ejemplo.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

Aunque ocasionalmente es conveniente, esta forma de sintaxis hace que el código sea difícil de leer y mantener. Por lo tanto, se recomienda que mantenga una instrucción en una línea.

## <a name="continuing-a-statement-over-multiple-lines"></a>Continuar con una declaración sobre varias líneas

Una instrucción normalmente cabe en una línea, pero cuando es demasiado larga, puede continuarla en la siguiente línea utilizando una secuencia de continuación de línea, que consta de un espacio seguido de un carácter de subrayado (`_`) seguido de un retorno de carro. En el ejemplo `MsgBox` siguiente, la instrucción ejecutable se continúa en dos líneas.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>Continuación implícita de la línea

En muchos casos, puede continuar una instrucción en la`_`siguiente línea consecutiva sin usar el carácter de subrayado ( ). Los siguientes elementos de sintaxis continúan implícitamente la instrucción en la siguiente línea de código.

- Después de`,`una coma ( ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- Después de un paréntesis abierto (`(`) o`)`antes de un paréntesis de cierre ( ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- Después de una`{`llave abierta ( ) o`}`antes de una llave de cierre ( ). Por ejemplo:

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    Para obtener más información, vea Inicializadores de [objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md) o inicializadores de [colección](./collection-initializers/index.md).

- Después de una`<%=`expresión incrustada abierta ( ) o`%>`antes del cierre de una expresión incrustada ( ) dentro de un literal XML. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   Para obtener más información, consulte [Expresiones incrustadas en XML](./xml/embedded-expressions-in-xml.md).

- Después del operador`&`de concatenación ( ). Por ejemplo:

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   Para obtener más información, consulte [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de`=` `&=`los `:=` `+=`operadores de asignación ( , , , `-=`, , `*=`, `/=`, `\=`, `^=`, `<<=`. `>>=` Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Para obtener más información, consulte [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de`+` `-`los `/` `*`operadores binarios ( `^` `>>`, `<<` `And`, `AndAlso` `Or`, `OrElse` `Like`, `Xor` `Mod` `<>`, `<`, , `>`, `<=`, `>=`, , , , , ) dentro de una expresión. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   Para obtener más información, consulte [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después `Is` `IsNot` de los operadores. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   Para obtener más información, consulte [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).

- Después de un`.`carácter calificador de miembro ( ) y antes del nombre del miembro. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   Sin embargo, debe incluir un`_`carácter de continuación de línea `With` ( ) después de un carácter calificador de miembro cuando utilice la instrucción o proporcione valores en la lista de inicialización para un tipo. Considere la posibilidad de romper la `=`línea después `With` del operador de asignación (por ejemplo, ) cuando utilice instrucciones o listas de inicialización de objetos. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   Para obtener más información, consulte [Con... Finalizar con inicializadores](../../../visual-basic/language-reference/statements/with-end-with-statement.md) de instrucción u [objeto: tipos con nombre y anónimos](./objects-and-classes/object-initializers-named-and-anonymous-types.md).

- Después de un`.` calificador de propiedad de eje XML ( o `.@` o `...`). Sin embargo, debe incluir un`_`carácter de continuación de línea `With` ( ) cuando especifique un calificador de miembro cuando utilice la palabra clave. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   Para obtener más información, consulte [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/index.md).

- Después de un signo menor que (<)`>`o antes de un signo mayor que ( ) cuando se especifica un atributo. También después de un`>`signo mayor que ( ) cuando se especifica un atributo. Sin embargo, debe incluir un`_`carácter de continuación de línea ( ) al especificar atributos de nivel de ensamblado o de nivel de módulo. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   Para obtener más información, consulte [Introducción a los atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md).

- Antes y después`Aggregate` `Distinct`de `From` `Group By`los `Group Join` `Join`operadores de consulta ( , `Into` `On`, `Ascending`, `Descending`, , , `Take` `Take While` `Where` `In` `Let` `Order By`, `Select`, `Skip`, `Skip While`, , , , , y ). No puede romper una línea entre las palabras clave de`Order By`los `Group Join` `Take While`operadores `Skip While`de consulta que se componen de varias palabras clave ( , , , y ). Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   Para obtener más información, consulte [Consultas](../../../visual-basic/language-reference/queries/index.md).

- Después `In` de `For Each` la palabra clave en una instrucción. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   Para obtener más información, consulte [Para cada... Siguiente instrucción](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- Después `From` de la palabra clave en un inicializador de colección. Por ejemplo:

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).

## <a name="adding-comments"></a>Adición de comentarios

El código fuente no siempre se explica por sí mismo, incluso para el programador que lo escribió. Para ayudar a documentar su código, por lo tanto, la mayoría de los programadores hacen uso liberal de los comentarios incrustados. Los comentarios en el código pueden explicar un procedimiento o una instrucción particular a cualquier persona que lo lea o trabaje con él más adelante. Visual Basic omite los comentarios durante la compilación y no afectan al código compilado.

Las líneas de comentario comienzan`'`con `REM` un apóstrofo ( ) o seguido de un espacio. Se pueden agregar en cualquier parte del código, excepto dentro de una cadena. Para anexar un comentario a una instrucción, inserte un apóstrofo o `REM` después de la instrucción, seguido del comentario. Los comentarios también pueden ir en su propia línea separada. En el ejemplo siguiente se muestran estas posibilidades.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>Comprobación de errores de compilación

Si, después de escribir una línea de código, la línea se muestra con un subrayado azul ondulado (también puede aparecer un mensaje de error), hay un error de sintaxis en la instrucción. Debe averiguar qué tiene que ver con la instrucción (buscando en la lista de tareas o pasando el cursor sobre el error con el puntero del mouse y leyendo el mensaje de error) y corregirlo. Hasta que haya corregido todos los errores de sintaxis en el código, el programa no se compilará correctamente.

## <a name="related-sections"></a>Secciones relacionadas

|Término|Definición|
|---|---|
|[Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)|Proporciona vínculos a páginas de `=` `*=`referencia `&=`de lenguaje que cubren operadores de asignación como , , y .|
|[Operadores y expresiones](./operators-and-expressions/index.md)|Muestra cómo combinar elementos con operadores para producir nuevos valores.|
|[Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Muestra cómo dividir una sola instrucción en varias líneas y cómo colocar varias instrucciones en la misma línea.|
|[Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Muestra cómo etiquetar una línea de código.|
