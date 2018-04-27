---
title: Instrucciones en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: beb33b8f2c30723158e41244cbb5c9cfca108a53
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="statements-in-visual-basic"></a>Instrucciones en Visual Basic
Una instrucción en Visual Basic es una instrucción completa. Puede contener palabras clave, operadores, variables, constantes y expresiones. Cada instrucción pertenece a una de las siguientes categorías:  
  
-   **Instrucciones de declaración**, que el nombre de una variable, constante o procedimiento y también puede especificar un tipo de datos.  
  
-   **Las instrucciones ejecutables**, que inician acciones. Estas instrucciones pueden llamar a un método o función, y puede crear un bucle o bifurcarse en bloques de código. Las instrucciones ejecutables incluyen **instrucciones de asignación**, que asigna un valor o expresión a una variable o constante.  
  
 Este tema describe cada categoría. Además, en este tema se describe cómo combinar varias instrucciones en una sola línea y cómo continuar una instrucción en varias líneas.  
  
## <a name="declaration-statements"></a>Instrucciones de declaración  
 Utilice las instrucciones de declaración para nombrar y definir procedimientos, variables, propiedades, matrices y constantes. Cuando se declara un elemento de programación, también puede definir su tipo de datos, el nivel de acceso y el ámbito. Para obtener más información, consulte [características de los elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 En el siguiente ejemplo contiene tres declaraciones.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 La primera declaración es la `Sub` instrucción. Junto con su búsqueda de coincidencias `End Sub` instrucción, declara un procedimiento denominado `applyFormat`. También especifica que `applyFormat` es `Public`, lo que significa que cualquier código que puede hacer referencia a él puede llamarlo.  
  
 La segunda declaración es la `Const` instrucción, que declara la constante `limit`, especificando la `Integer` tipo de datos y un valor de 33.  
  
 La tercera declaración es la `Dim` instrucción, que declara la variable `thisWidget`. El tipo de datos es un objeto concreto, es decir, se crea un objeto desde el `Widget` clase. Puede declarar una variable de cualquier tipo de datos básico o de cualquier tipo de objeto que se expone en la aplicación que esté utilizando.  
  
### <a name="initial-values"></a>Valores iniciales  
 Cuando se ejecuta el código que contiene una instrucción de declaración, Visual Basic reserva la memoria necesaria para el elemento declarado. Si el elemento contiene un valor, Visual Basic la inicializa con el valor predeterminado para su tipo de datos. Para obtener más información, vea "Comportamiento" en [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Puede asignar un valor inicial a una variable como parte de su declaración, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Si una variable es una variable de objeto, puede crear explícitamente una instancia de la clase cuando se declara mediante el uso de la [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md) palabra clave, como en el ejemplo siguiente se muestra.  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Tenga en cuenta que el valor inicial especificado en una instrucción de declaración no se asigna a una variable hasta que la ejecución llega a su instrucción de declaración. Hasta ese momento, la variable contiene el valor predeterminado para su tipo de datos.  
  
## <a name="executable-statements"></a>Instrucciones ejecutables  
 Una instrucción ejecutable realiza una acción. Puede llamar a un procedimiento, rama a otro lugar en el código, recorrer varias instrucciones, o evaluar una expresión. Una instrucción de asignación es un caso especial de una instrucción ejecutable.  
  
 En el ejemplo siguiente se usa un `If...Then...Else` estructura para ejecutar diferentes bloques de código en función del valor de una variable de control. Dentro de cada bloque de código, un `For...Next` un número especificado de veces que ejecuta el bucle.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 El `If` instrucción en el ejemplo anterior comprueba el valor del parámetro `clockwise`. Si el valor es `True`, llama a la `spinClockwise` método `aWidget`. Si el valor es `False`, llama a la `spinCounterClockwise` método `aWidget`. El `If...Then...Else` estructura de control finaliza con `End If`.  
  
 El `For...Next` bucle dentro de cada bloque llama al método adecuado un número de veces igual al valor de la `revolutions` parámetro.  
  
## <a name="assignment-statements"></a>Instrucciones de asignación  
 Instrucciones de asignación realizan operaciones de asignación, que consisten en tomar el valor en el lado derecho del operador de asignación (`=`) y almacenarla en el elemento de la izquierda, como en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 En el ejemplo anterior, la instrucción de asignación almacena el valor literal 42 en la variable `v`.  
  
### <a name="eligible-programming-elements"></a>Elementos de programación válidos  
 El elemento de programación en el lado izquierdo del operador de asignación debe ser capaz de Aceptar y almacenar un valor. Esto significa que debe ser una variable o propiedad que no es [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), o debe ser un elemento de matriz. En el contexto de una instrucción de asignación, este tipo de elementos se denomina a veces un *valor l*, "valor izquierdo".  
  
 El valor en el lado derecho del operador de asignación se genera mediante una expresión, que puede constar de cualquier combinación de literales, constantes, variables, propiedades, elementos de matriz, otras expresiones o llamadas de función. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 En el ejemplo anterior, se agrega el valor almacenado en la variable `y` al valor almacenado en la variable `z`y, a continuación, agrega el valor devuelto por la llamada a función `findResult`. El valor total de esta expresión, a continuación, se almacena en la variable `x`.  
  
### <a name="data-types-in-assignment-statements"></a>Tipos de datos en instrucciones de asignación  
 Además de valores numéricos, el operador de asignación también puede asignar `String` valores, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 También puede asignar `Boolean` valores, ya sea mediante un `Boolean` literal o un `Boolean` expresión, como en el ejemplo siguiente se muestra.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 De forma similar, puede asignar los valores adecuados a elementos de programación de la `Char`, `Date`, o `Object` tipo de datos. También puede asignar una instancia de objeto a un elemento que se declara de la clase desde el que se creó esa instancia.  
  
### <a name="compound-assignment-statements"></a>Instrucciones de asignación compuesta  
 *Instrucciones de asignación compuesta* realizar primero una operación en una expresión antes de asignarlo a un elemento de programación. En el ejemplo siguiente se muestra uno de estos operadores, `+=`, lo que aumenta el valor de la variable en el lado izquierdo del operador con el valor de la expresión situada a la derecha.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 En el ejemplo anterior se suma 1 al valor de `n`y, a continuación, almacena ese nuevo valor en `n`. Es un método abreviado equivalente de la siguiente instrucción:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Una serie de operaciones de asignación compuesta se puede realizar con operadores de este tipo. Para obtener una lista de estos operadores y más información sobre ellos, vea [operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 El operador de asignación de concatenación (`&=`) es útil para agregar una cadena al final de la lista ya cadenas, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>Conversiones de tipos en instrucciones de asignación  
 El valor que se asigna a una variable, propiedad o elemento de matriz debe ser de un tipo de datos apropiado para ese elemento de destino. En general, debe intentar generar un valor del mismo tipo de datos que el elemento de destino. Sin embargo, algunos tipos se pueden convertir a otros tipos durante la asignación.  
  
 Para obtener información sobre cómo convertir entre tipos de datos, vea [conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md). En resumen, Visual Basic convierte automáticamente un valor de un tipo determinado en cualquier otro tipo a la que se amplía. A *conversión de ampliación* es aquella que siempre se realiza correctamente en tiempo de ejecución y no se perderá ningún dato. Por ejemplo, Visual Basic convierte un `Integer` valor `Double` cuando sea necesario, porque `Integer` se amplía a `Double`. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 *Conversiones de restricción* (aquellos que no son de ampliación) llevan un riesgo de error en tiempo de ejecución, o de pérdida de datos. Puede realizar una conversión de restricción explícitamente mediante una función de conversión de tipo, o puede indicar al compilador que realice implícitamente todas las conversiones estableciendo `Option Strict Off`. Para obtener más información, consulte [conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## <a name="putting-multiple-statements-on-one-line"></a>Colocar varias instrucciones en una sola línea  
 Puede tener varias instrucciones en una sola línea, separada por dos puntos (`:`) caracteres. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Aunque ocasionalmente puede resultar conveniente, esta forma de sintaxis hace que el código difícil de leer y mantener. Por lo tanto, se recomienda que mantenga una instrucción en una línea.  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>Continuar una instrucción en varias líneas  
 Una instrucción normalmente se ajusta en una sola línea, pero cuando es demasiado larga, puede continuar en la siguiente línea mediante una secuencia de continuación de línea, que consta de un espacio seguido por un carácter de subrayado (`_`) seguido por un retorno de carro. En el ejemplo siguiente, la `MsgBox` instrucción ejecutable continúa en dos líneas.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>Continuación de línea implícita  
 En muchos casos, puede continuar una instrucción en la línea consecutiva siguiente sin utilizar el carácter de subrayado (_). En la tabla siguiente se enumera los elementos de sintaxis que continúan implícitamente la instrucción en la siguiente línea de código.  
  
|Elemento de sintaxis|Ejemplo|  
|---|---|  
|Después de una coma (`,`).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|Después de un paréntesis de apertura (`(`) o antes de un paréntesis de cierre (`)`).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|Después de una llave de apertura (`{`) o antes de una llave de cierre (`}`).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) o [inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|Una vez abierto expresión incrustada (`<%=`) o antes del cierre de una expresión incrustada (`%>`) dentro de un literal XML.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|Después del operador de concatenación (`&`).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de los operadores de asignación (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de los operadores binarios (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) en una expresión.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de la `Is` y `IsNot` operadores.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Para obtener más información, consulte [operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de un carácter de calificador de miembro (`.`) y antes del nombre de miembro. Sin embargo, debe incluir un carácter de continuación de línea (_) después de un carácter de calificador de miembro cuando utilizas el `With` instrucción o proporcionar valores de la lista de inicialización para un tipo. Considere la posibilidad de dividir la línea después del operador de asignación (por ejemplo, `=`) cuando se utiliza `With` instrucciones o listas de inicialización de objetos.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Para obtener más información, consulte [con... Terminar con la instrucción](../../../visual-basic/language-reference/statements/with-end-with-statement.md) o [inicializadores de objeto: tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|Después de un calificador de propiedad de eje XML (`.` o `.@` o `...`). Sin embargo, debe incluir un carácter de continuación de línea (_) al especificar un calificador de miembro cuando se usa el `With` palabra clave.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Para obtener más información, consulte [propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|Después de una menor-inicio de sesión (<) o antes de una mayor-de inicio de sesión (`>`) cuando se especifica un atributo. También después de una mayor-de inicio de sesión (`>`) cuando se especifica un atributo. Sin embargo, debe incluir un carácter de continuación de línea (_) al especificar atributos de nivel de ensamblado o de nivel de módulo.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Para obtener más información, consulte [información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md).|  
|Antes y después de los operadores de consulta (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, y `Descending`). No se puede dividir una línea entre las palabras clave de operadores de consulta que se componen de varias palabras clave (`Order By`, `Group Join`, `Take While`, y `Skip While`).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Para obtener más información, consulte [consultas](../../../visual-basic/language-reference/queries/queries.md).|  
|Después de la `In` palabra clave en un `For Each` instrucción.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Para obtener más información, vea [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|Después de la `From` palabra clave en un inicializador de colección.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## <a name="adding-comments"></a>Agregar comentarios  
 Código fuente no siempre es fácil de entender, incluso para el programador que lo ha escrito. Con el fin de documentar el código, por lo tanto, los programadores utilizan libremente comentarios incrustados. Comentarios en código pueden explicar un procedimiento o una instrucción concreta a cualquiera que lea o trabaje con ellos posteriormente. Visual Basic omite los comentarios durante la compilación y no afectan al código compilado.  
  
 Líneas de comentario comienzan con un apóstrofo (`'`) o `REM` seguido por un espacio. Se pueden agregar en cualquier lugar en el código, excepto en una cadena. Para anexar un comentario a una instrucción, inserte un apóstrofo o `REM` después de la instrucción, seguida del comentario. Los comentarios también pueden ir en su propia línea independiente. En el ejemplo siguiente se muestra estas posibilidades.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>Comprobación de errores de compilación  
 Si, después de escribir una línea de código, la línea se muestra con un subrayado ondulado de color azul (también puede aparecer un mensaje de error), hay un error de sintaxis en la instrucción. Debe averiguar cuál es el problema con la instrucción (de búsqueda en la lista de tareas, o el mouse sobre el error con el puntero del mouse y leer el mensaje de error) y corregirlo. Hasta que corrija todos los errores de sintaxis en el código, el programa no se compilará correctamente.  
  
## <a name="related-sections"></a>Secciones relacionadas  
  
|Término|de esquema JSON|  
|---|---|  
|[Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)|Proporciona vínculos a páginas de referencia del lenguaje que describen los operadores de asignación como `=`, `*=`, y `&=`.|  
|[Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Muestra cómo combinar elementos con operadores para obtener nuevos valores.|  
|[Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Muestra cómo dividir una única instrucción en varias líneas y cómo colocar varias instrucciones en la misma línea.|  
|[Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Muestra cómo etiquetar una línea de código.|
