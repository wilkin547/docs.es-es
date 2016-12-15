---
title: "Instrucciones en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "subrayado azul"
  - "dos puntos (:)"
  - "constantes, definir"
  - "constantes, instrucciones"
  - "instrucciones ejecutables"
  - "saltos de línea, en el código"
  - "procedimientos, instrucciones"
  - "instrucciones [Visual Basic], acerca de las instrucciones"
  - "subrayados"
  - "variables [Visual Basic], asignar"
  - "variables [Visual Basic], declarar"
  - "variables [Visual Basic], definir"
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Instrucciones en Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], una instrucción es una instrucción completa.  Puede contener palabras clave, operadores, variables, constantes y expresiones.  Cada instrucción pertenece a una de las categorías siguientes:  
  
-   **Instrucciones de declaración**, que dan nombre a una variable, constante o procedimiento y también pueden especificar un tipo de datos.  
  
-   **Instrucciones ejecutables**, que inician acciones.  Estas instrucciones pueden llamar a un método o función, y pueden  repetires en bloques de código o crear una bifurcación en otro bloque de código.  Las instrucciones ejecutables incluyen **instrucciones de asignación**, que asignan un valor o expresión a una variable o constante.  
  
 En este tema se describe cada categoría.  Asimismo, en este tema se describe cómo combinar varias instrucciones en una sola línea y cómo continuar una instrucción en varias líneas.  
  
## Instrucciones de declaración  
 Las instrucciones de declaración se utilizan para definir procedimientos, variables, propiedades, matrices y constantes, y asignarles nombre.  Cuando se declara un elemento de programación, también se puede definir su tipo de datos, nivel de acceso y ámbito.  Para obtener más información, vea [Características de los elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
 El siguiente ejemplo contiene tres declaraciones.  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 La primera declaración es la instrucción `Sub`.  Junto con su instrucción `End Sub` correspondiente, declara un procedimiento denominado `applyFormat`.  También especifica que `applyFormat` es `Public`, lo que quiere decir que cualquier código que pueda hacer referencia a ella, puede también llamarla.  
  
 La segunda declaración es la instrucción `Const`, que declara la constante `limit`, que especifica el tipo de datos `Integer` y un valor de 33.  
  
 La tercera declaración es la instrucción `Dim`, que declara la variable `thisWidget`.  El tipo de datos es un objeto concreto, específicamente un objeto creado a partir de la clase `Widget`.  Puede declarar una variable para que sea de cualquier tipo de datos elemental o de cualquier tipo de objeto que esté expuesto a la aplicación que está usando.  
  
### Valores iniciales  
 Cuando se ejecuta el código que contiene una declaración de instrucción, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] reserva la memoria necesaria para el elemento declarado.  Si el elemento contiene un valor, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] lo inicializa al valor predeterminado para su tipo de datos.  Para obtener más información, vea "Comportamiento" en [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
 Puede asignar un valor inicial a una variable como parte de su declaración, como se puede ver en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 Si la variable es una variable de objeto, al declararla puede crear de forma explícita una instancia de su clase utilizando la palabra clave [New \(Operador\)](../../../visual-basic/language-reference/operators/new-operator.md), como se muestra a continuación:  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 Observe que el valor inicial especificado en una instrucción de declaración no se asigna a una variable hasta que la ejecución llega a su instrucción de declaración.  Hasta ese momento, la variable contiene el valor predeterminado para su tipo de datos.  
  
## Instrucciones ejecutables  
 Una instrucción ejecutable realiza una acción.  Puede llamar a un procedimiento, bifurcar a otra parte del código, recorrer varias instrucciones con un bucle o evaluar una expresión.  Una instrucción de asignación es un caso especial de una instrucción ejecutable.  
  
 En el ejemplo siguiente se utiliza una estructura de control `If...Then...Else` para ejecutar diferentes bloques de código basándose en el valor de una variable.  En cada bloque de código, un bucle `For...Next` se ejecuta un número especificado de veces.  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 Después, la instrucción `If` del ejemplo anterior comprueba el valor del parámetro `clockwise`.  Si el valor es `True`, llama al método `spinClockwise` de `aWidget`.  Si el valor es `False`, llama al método `spinCounterClockwise` de `aWidget`.  La estructura de control `If...Then...Else` finaliza con `End If`.  
  
 El bucle `For...Next` de cada bloque llama al método adecuado un número de veces igual al valor del parámetro `revolutions`.  
  
## Instrucciones de asignación  
 Las instrucciones de asignación realizan operaciones de asignación, que consisten en tomar el valor de la derecha del operador de asignación \(`=`\) y almacenarlo en el elemento de la izquierda, como en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 En el ejemplo anterior, la instrucción de asignación almacena el valor literal 42 en la variable `v`.  
  
### Elementos de programación elegibles  
 El elemento de programación del lado izquierdo del operador de asignación debe poder aceptar y almacenar un valor.  Esto significa que debe ser una variable o propiedad que no es [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), o debe ser un elemento de matriz.  En el contexto de una instrucción de asignación, este tipo de elemento a veces se denomina *valor l*, que significa "valor de la izquierda".  
  
 El valor del lado derecho del operador de asignación se genera mediante una expresión que puede estar formada por cualquier combinación de literales, constantes, variables, propiedades, elementos de matriz, otras expresiones o llamadas a función.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 En el ejemplo anterior se agrega el valor almacenado en la variable `y` al valor almacenado en la variable `z` y, a continuación, se agrega el valor que devuelve la llamada a la función `findResult`.  El valor total de esta expresión se almacena en la variable `x`.  
  
### Tipos de datos en instrucciones de asignación  
 Además de valores numéricos, el operador de asignación también puede asignar valores `String`, tal como muestra el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 También se pueden asignar valores `Boolean` utilizando un literal `Boolean` o una expresión `Boolean`, tal como muestra el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 Igualmente, se pueden asignar valores adecuados a elementos de programación del tipo de datos `Char`, `Date` u `Object`.  También se puede asignar una instancia de objeto a un elemento declarado como miembro de la clase a partir de la que se crea esa instancia.  
  
### Instrucciones de asignación compuesta  
 Las *instrucciones de asignación compuesta* realizan primero una operación en una expresión antes de asignarla a un elemento de programación.  En el siguiente ejemplo se muestra uno de estos operadores, `+=`, que incrementa el valor de la variable del lado izquierdo del operador con el valor de la expresión de la derecha.  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 En el ejemplo anterior se suma 1 al valor de `n` y, a continuación, el nuevo valor se almacena en `n`.  Es el equivalente abreviado de la siguiente instrucción:  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 Mediante el uso de este tipo de operadores, puede realizarse una serie de operaciones de asignación compuestas.  Para obtener una lista de estos operadores y más información sobre ellos, vea [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md).  
  
 El operador de asignación de concatenación \(`&=`\) es útil para agregar una cadena al final de cadenas existentes, como se muestra en este ejemplo.  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### Conversiones de tipos en instrucciones de asignación  
 El valor que se asigna a una variable, propiedad o elemento de matriz debe ser de un tipo de datos apropiado para el elemento de destino.  En general, hay que intentar generar un valor del mismo tipo de datos que el del elemento de destino.  Sin embargo, algunos tipos se pueden convertir en otros tipos durante la asignación.  
  
 Para obtener información sobre cómo convertir entre tipos de datos, vea [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md).  En pocas palabras, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte automáticamente un valor de un tipo dado en cualquier otro tipo al que amplia.  Una *conversión de ampliación* es aquella que siempre se produce en tiempo de ejecución y no pierde datos.  Por ejemplo, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte un valor `Integer` en `Double` cuando conviene, porque `Integer` se amplia a `Double`.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Las *conversiones de restricción* \(las que no son de ampliación\) conllevan el riesgo de error o de pérdida de datos en tiempo de ejecución.  Las conversiones de restricción se pueden realizar explícitamente mediante una función de conversión de tipos, o se puede indicar al compilador que realice implícitamente todas las conversiones estableciendo `Option Strict Off`.  Para obtener más información, vea [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## Colocar varias instrucciones en una línea  
 Se pueden tener varias instrucciones en una sola línea separadas por el carácter de dos puntos \(`:`\).  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 Aunque ocasionalmente puede resultar conveniente, esta forma de sintaxis dificulta la lectura y el mantenimiento del código.  Por tanto, se recomienda mantener una instrucción por línea.  
  
## Continuar una instrucción en varias líneas  
 Normalmente, una línea suele ser suficiente para una instrucción, pero si la instrucción es demasiado larga, se puede continuar en la siguiente línea mediante una secuencia de continuación de línea, que está compuesta por un espacio seguido de un carácter de subrayado \(`_`\) y de un retorno de carro.  En el siguiente ejemplo, la instrucción ejecutable `MsgBox` continúa en más de dos líneas.  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### Continuación de línea implícita  
 En muchos casos, puede continuar una instrucción en la línea consecutiva siguiente sin utilizar el carácter de subrayado \(\_\).  En la tabla siguiente se enumeran los elementos de sintaxis que continúan implícitamente la instrucción en la línea de código siguiente.  
  
|||  
|-|-|  
|Elemento de sintaxis|Ejemplo|  
|Después de una coma \(`,`\).|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|Después de un paréntesis de apertura \(`(`\) o antes de un paréntesis de cierre \(`)`\).|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|Después de una llave de apertura \(`{`\) o antes de una llave de cierre \(`}`\).|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> Para obtener más información, vea [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) o [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
|Después de la apertura de una expresión incrustada \(`<%=`\) o antes del cierre de una expresión incrustada \(`%>`\) dentro de un literal XML.|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> Para obtener más información, vea [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
|Después del operador de concatenación \(`&`\).|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> Para obtener más información, vea [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de operadores de asignación \(`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`\).|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> Para obtener más información, vea [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de operadores binarios \(`+`, `-`, `/`, `*``Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`\) dentro de una expresión.|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> Para obtener más información, vea [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de los operadores `Is` e `IsNot`.|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> Para obtener más información, vea [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).|  
|Después de un carácter de calificador de miembro \(`.`\) y antes del nombre de miembro.  Sin embargo, debe incluir un carácter de continuación de línea \(\_\) a continuación de un carácter de calificador de miembro cuando esté utilizando la instrucción `With` o proporcionando valores en la lista de inicialización para un tipo.  Considere la posibilidad de interrumpir la línea después del operador de asignación \(por ejemplo, `=`\) cuando esté utilizando instrucciones `With` o listas de inicialización de objetos.|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> Para obtener más información, vea [With...End With \(Instrucción\)](../../../visual-basic/language-reference/statements/with-end-with-statement.md) o [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).|  
|Después de un calificador de propiedad de eje XML \(`.` o `.@` o `...`\).  Sin embargo, debe incluir un carácter de continuación de línea \(\_\) al especificar un calificador de miembro cuando esté utilizando la palabra clave `With`.|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> Para obtener más información, vea [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).|  
|Después de un signo menor que \(\<\) o antes de un signo mayor que \(`>`\) al especificar un atributo.  También, después de un signo mayor que \(`>`\) al especificar un atributo.  Sin embargo, debe incluir un carácter de continuación de línea \(\_\) al especificar atributos de nivel de ensamblado o de nivel de módulo.|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> Para obtener más información, vea [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).|  
|Antes de y después de operadores de consulta \(`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending` y `Descending`\).  No puede interrumpir una línea entre las palabras clave de operadores de consulta que se componen de varias palabras clave \(`Order By`, `Group Join`, `Take While` y `Skip While`\).|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> Para obtener más información, vea [Consultas](../../../visual-basic/language-reference/queries/queries.md).|  
|Después de la palabra clave `In` en una instrucción `For Each`.|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> Para obtener más información, vea [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md).|  
|Después de la palabra clave `From` en un inicializador de colección.|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> Para obtener más información, vea [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).|  
  
## Agregar comentarios  
 El código fuente no es siempre fácil de entender, ni siquiera para el programador que lo escribió.  Por consiguiente, como ayuda para documentar el código, la mayoría de los programadores utilizan libremente comentarios incrustados.  Los comentarios en el código pueden explicar un procedimiento o una instrucción concreta a cualquiera que los lea o trabaje con ellos posteriormente.  En [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], los comentarios se omiten durante la compilación y no afectan al código compilado.  
  
 Las líneas de comentario comienzan con un apóstrofo \(`'`\) o `REM` seguido de un espacio.  Se pueden agregar en cualquier parte del código, excepto en una cadena.  Para anexar un comentario a una instrucción, inserte un apóstrofo o `REM` después de la instrucción, seguido del comentario.  Los comentarios también pueden escribirse separados en una línea propia.  En el ejemplo siguiente se muestran estas posibilidades.  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## Comprobar errores de compilación  
 Si después de escribir una línea de código, la línea se muestra con un subrayado azul con líneas onduladas \(también puede mostrarse un mensaje de error\), la instrucción contiene un error de sintaxis.  Debe averiguar cuál es el problema en la instrucción y corregirlo; para ello, busque en la lista de tareas o desplace el puntero del mouse sobre el error y lea el mensaje de error\).  Mientras no corrija todos los errores de sintaxis del código, el programa no se compilará correctamente.  
  
## Secciones relacionadas  
  
|||  
|-|-|  
|Término|Definición|  
|[Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)|Proporciona vínculos a páginas de referencia del lenguaje que describen los operadores de asignación, como `=`, `*=` y `&=`.|  
|[Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|Muestra cómo combinar elementos con operadores para obtener nuevos valores.|  
|[Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|Muestra cómo dividir una instrucción única en varias líneas y cómo colocar varias instrucciones en la misma línea.|  
|[Cómo: Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|Muestra cómo etiquetar una línea de código.|