---
title: "Función (instrucción, Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: af87477f81fab8406d726ebc8c81260b371d71c8
ms.lasthandoff: 03/13/2017

---
# <a name="function-statement-visual-basic"></a>Function (Instrucción, Visual Basic)
Declara el nombre, parámetros y código que definen un `Function` procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Elementos  
  
-   `attributelist`  
  
     Opcional. Consulte [lista de los atributos](attribute-list.md).  
  
-   `accessmodifier`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Consulte [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Opcional. Consulte [compartido](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Opcional. Consulte [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Opcional. Consulte [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Obligatorio. Nombre del procedimiento. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [escriba List](type-list.md).  
  
-   `parameterlist`  
  
     Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Consulte [lista de parámetros](parameter-list.md).  
  
-   `returntype`  
  
     Requerido si `Option Strict` es `On`. Tipo de datos del valor devuelto por este procedimiento.  
  
-   `Implements`  
  
     Opcional. Indica que este procedimiento implementa uno o varios `Function` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Consulte [implementa instrucción](implements-statement.md).  
  
-   `implementslist`  
  
     Es necesario si se proporciona `Implements`. Lista de procedimientos `Function` que se implementan.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:  
  
     `interface.definedname`  
  
    |Parte|Descripción|  
    |---|---|  
    |`interface`|Obligatorio. Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.|  
    |`definedname`|Obligatorio. Nombre por el que se define el procedimiento en `interface`.|  
  
-   `Handles`  
  
     Opcional. Indica que este procedimiento puede controlar uno o más eventos específicos. Consulte [controla](handles-clause.md).  
  
-   `eventlist`  
  
     Es necesario si se proporciona `Handles`. Lista de eventos que controla este procedimiento.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Cada `eventspecifier` tiene la sintaxis y las partes siguientes:  
  
     `eventvariable.event`  
  
    |Parte|Descripción|  
    |---|---|  
    |`eventvariable`|Obligatorio. Variable de objeto declarada con el tipo de datos de la clase o estructura que provoca el evento.|  
    |`event`|Obligatorio. Nombre del evento que controla este procedimiento.|  
  
-   `statements`  
  
     Opcional. Bloque de instrucciones que se ejecutan dentro de este procedimiento.  
  
-   `End Function`  
  
     Termina la definición de este procedimiento.  
  
## <a name="remarks"></a>Comentarios  
 El código ejecutable debe estar dentro de un procedimiento. A su vez, cada procedimiento, se declara dentro de una clase, una estructura o un módulo que se conoce como la clase, estructura o módulo que lo contiene.  
  
 Para devolver un valor al código de llamada, use un `Function` procedimiento; en caso contrario, utilice un `Sub` procedimiento.  
  
## <a name="defining-a-function"></a>Definición de una función  
 Puede definir un `Function` procedimiento sólo en el nivel de módulo. Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, consulte [contextos de declaración y niveles de acceso predeterminados](declaration-contexts-and-default-access-levels.md).  
  
 `Function`valor predeterminado de procedimientos para acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso.  
  
 Un `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento. Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz. Si no especifica la `returntype` parámetro, el procedimiento devuelve `Object`.  
  
 Si este procedimiento utiliza el `Implements` (palabra clave), la clase o estructura contenedora también debe tener un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción. El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`. Sin embargo, el nombre por el que una interfaz define la `Function` (en `definedname`) no es necesario que coincida con el nombre de este procedimiento (en `name`).  
  
> [!NOTE]
>  Puede usar expresiones lambda para definir la función inline de expresiones. Para obtener más información, consulte [expresión de función](../../../visual-basic/language-reference/operators/function-expression.md) y [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Devolver desde una función  
 Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.  
  
 Para devolver un valor desde una función, puede asignar el valor al nombre de función o incluirlo en una `Return` instrucción.  
  
 El `Return` instrucción simultáneamente asigna el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrStatements&#24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction` y, a continuación, usa el `Exit Function` instrucción para devolver.  
  
 [!code-vb[23 de VbVbalrStatements #](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 El `Exit Function` y `Return` instrucciones provocan una salida inmediata de un `Function` procedimiento. Cualquier número de `Exit Function` y `Return` instrucciones pueden aparecer en cualquier parte en el procedimiento y puede combinar `Exit Function` y `Return` instrucciones.  
  
 Si utiliza `Exit Function` sin asignar un valor a `name`, el procedimiento devuelve el valor predeterminado para el tipo de datos que se especifica en `returntype`. Si `returntype` no se especifica, el procedimiento devuelve `Nothing`, que es el valor predeterminado de `Object`.  
  
## <a name="calling-a-function"></a>Llamar a una función  
 Se llama a un `Function` procedimiento utilizando el nombre del procedimiento, seguido por la lista de argumentos entre paréntesis, en una expresión. Puede omitir los paréntesis sólo si no se proporciona ningún argumento. Sin embargo, el código es más legible si se incluyen siempre los paréntesis.  
  
 Se llama a un `Function` procedimiento del mismo modo que se llama a cualquier biblioteca funcione como `Sqrt`, `Cos`, o `ChrW`.  
  
 También puede llamar a una función utilizando la `Call` (palabra clave). En ese caso, se omite el valor devuelto. El uso de la `Call` palabra clave no se recomienda en la mayoría de los casos. Para obtener más información, consulte [instrucción Call](call-statement.md).  
  
 Visual Basic reorganiza a veces las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, no debe utilizar un `Function` procedimiento en una expresión aritmética cuando la función cambie el valor de variables en la misma expresión.  
  
## <a name="async-functions"></a>Funciones asincrónicas  
 El *Async* característica le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas o dividir manualmente el código en varias funciones o expresiones lambda.  
  
 Si marca una función con el [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador, puede utilizar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en la función. Cuando el control alcanza un `Await` expresión en la `Async` (función), el control vuelve al llamador y progreso de la función se suspende hasta que se complete la tarea esperada. Una vez completada la tarea, puede reanudar la ejecución de la función.  
  
> [!NOTE]
>  Un `Async` procedimiento vuelve al llamador cuando encuentra el primer objeto esperado que aún no se ha completado o se llega al final de la `Async` procedimiento, lo que ocurra primero.  
  
 Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>o <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Un ejemplo de un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>se muestra a continuación.</xref:System.Threading.Tasks.Task%601>  
  
 Un `Async` función no puede declarar ningún [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parámetros.  
  
 Un [Sub (instrucción)](sub-statement.md) también se pueden marcar con el `Async` modificador. Esto se utiliza principalmente para controladores de eventos, donde no se puede devolver un valor. Un `Async``Sub` procedimiento no se puede esperar y el llamador de un `Async``Sub` procedimiento no puede detectar las excepciones producidas por el `Sub` procedimiento.  
  
 Para obtener más información acerca de `Async` funciones, vea [la programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [Async devolver tipos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Funciones de iterador  
 Un *iterador* función realiza una iteración personalizada sobre una colección, como una lista o matriz. Una función de iterador utiliza la [producen](yield-statement.md) instrucción para devolver cada elemento de uno en uno. Cuando un [producen](yield-statement.md) se alcanza la instrucción, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función de iterador.  
  
 Llamar a un iterador desde código de cliente mediante un [For Each... Siguiente](for-each-next-statement.md) instrucción.  
  
 Puede ser el tipo de valor devuelto de una función de iterador <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
 Para más información, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la `Function` instrucción para declarar el nombre, parámetros y código que forman el cuerpo de un `Function` procedimiento. El `ParamArray` modificador permite que la función aceptar un número variable de argumentos.  
  
 [!code-vb[VbVbalrStatements&#25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.  
  
 [!code-vb[26 de VbVbalrStatements #](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `DelayAsync` es una `Async``Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`. Dado que el tipo devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un número entero. Esto se muestra en esta instrucción: `Dim result As Integer = Await delayTask`.  
  
 El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento. Porque `DoSomethingAsync` es una `Async` (función), la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`. El `startButton_Click``Sub` procedimiento debe definirse con la `Async` modificador porque tiene un `Await` expresión.  
  
 [!code-vb[csAsyncMethod n.º&1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Sub (instrucción)](sub-statement.md)   
 [Function (procedimientos)](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Lista de parámetros](parameter-list.md)   
 [Dim (instrucción)](dim-statement.md)   
 [Call (instrucción)](call-statement.md)   
 [Of](of-clause.md)   
 [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Cómo: utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Procedimientos de solución de problemas](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Expresión de función](../../../visual-basic/language-reference/operators/function-expression.md)
