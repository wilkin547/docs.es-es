---
title: "Sub (instrucción) (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
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
ms.openlocfilehash: 0eb78f92f22502d9e8595051361b45d9bf53ed64
ms.lasthandoff: 03/13/2017

---
# <a name="sub-statement-visual-basic"></a>Sub (Instrucción, Visual Basic)
Declara el nombre, parámetros y código que definen un `Sub` procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Elementos  
  
-   `attributelist`  
  
     Opcional. Consulte [lista de los atributos](attribute-list.md).  
  
-   `Partial`  
  
     Opcional. Indica la definición de un método parcial. Consulte [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Consulte [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Sobrecargas](../modifiers/overloads.md)  
  
    -   [Overrides](../modifiers/overrides.md)  
  
    -   [Overridable](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Opcional. Consulte [compartido](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Opcional. Consulte [sombras](../modifiers/shadows.md).  
  
-   `Async`  
  
     Opcional. Consulte [Async](../modifiers/async.md).  
  
-   `name`  
  
     Obligatorio. Nombre del procedimiento. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento para la `New` (palabra clave). Para obtener más información, consulte [duración de los objetos: cómo los objetos son crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Opcional. Lista de parámetros de tipo para un procedimiento genérico. Consulte [escriba List](type-list.md).  
  
-   `parameterlist`  
  
     Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Consulte [lista de parámetros](parameter-list.md).  
  
-   `Implements`  
  
     Opcional. Indica que este procedimiento implementa uno o varios `Sub` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Consulte [implementa instrucción](implements-statement.md).  
  
-   `implementslist`  
  
     Es necesario si se proporciona `Implements`. Lista de procedimientos `Sub` que se implementan.  
  
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
  
-   `End Sub`  
  
     Termina la definición de este procedimiento.  
  
## <a name="remarks"></a>Comentarios  
 El código ejecutable debe estar dentro de un procedimiento. Use un `Sub` procedimiento cuando no desea devolver un valor al código de llamada. Use un `Function` procedimiento cuando desee devolver un valor.  
  
## <a name="defining-a-sub-procedure"></a>Definición de un procedimiento Sub  
 Puede definir un `Sub` procedimiento sólo en el nivel de módulo. El contexto de la declaración de un procedimiento sub por lo tanto, debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, consulte [contextos de declaración y niveles de acceso predeterminados](declaration-contexts-and-default-access-levels.md).  
  
 `Sub`valor predeterminado de procedimientos para acceso público. Puede ajustar los niveles de acceso mediante los modificadores de acceso.  
  
 Si el procedimiento utiliza el `Implements` (palabra clave), la clase o estructura contenedora debe tener un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción. El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`. Sin embargo, el nombre por el que una interfaz define la `Sub` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Devolver desde un procedimiento Sub  
 Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.  
  
 En el ejemplo siguiente se muestra cómo volver de un `Sub` procedimiento.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 El `Exit Sub` y `Return` instrucciones provocan una salida inmediata de un `Sub` procedimiento. Cualquier número de `Exit Sub` y `Return` instrucciones pueden aparecer en cualquier parte en el procedimiento y puede combinar `Exit Sub` y `Return` instrucciones.  
  
## <a name="calling-a-sub-procedure"></a>Llamar a un procedimiento Sub  
 Se llama a un `Sub` procedimiento mediante el nombre del procedimiento en una instrucción y, a continuación, ese nombre con su lista de argumentos entre paréntesis. Puede omitir los paréntesis sólo si no se proporciona ningún argumento. Sin embargo, el código es más legible si se incluyen siempre los paréntesis.  
  
 Un `Sub` procedimiento y un `Function` procedimiento puede tener parámetros y realizar una serie de instrucciones. Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` procedimiento no. Por lo tanto, no puede usar un `Sub` procedimiento en una expresión.  
  
 Puede usar el `Call` palabra clave cuando se llama a un `Sub` procedimiento pero que la palabra clave no se recomienda para la mayoría de los casos. Para obtener más información, consulte [instrucción Call](call-statement.md).  
  
 Visual Basic reorganiza a veces las expresiones aritméticas para aumentar la eficacia interna. Por ese motivo, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que las expresiones se llamará en un orden concreto.  
  
## <a name="async-sub-procedures"></a>Async Sub (procedimientos)  
 Mediante el uso de la característica Async, puede invocar funciones asincrónicas sin usar devoluciones de llamada explícitas o dividir manualmente el código en varias funciones o expresiones lambda.  
  
 Si marca un procedimiento con el [Async](../modifiers/async.md) modificador, puede utilizar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el procedimiento. Cuando el control alcanza un `Await` expresión en el `Async` procedimiento, el control vuelve al llamador y el progreso en el procedimiento se suspende hasta que se complete la tarea esperada. Una vez completada la tarea, puede reanudar la ejecución del procedimiento.  
  
> [!NOTE]
>  Un `Async` procedimiento vuelve al llamador cuando se encuentra en el primer objeto esperado que aún no se ha completado o el final de la `Async` se alcanza el procedimiento, lo que ocurra primero.  
  
 También puede marcar un [Function (instrucción)](function-statement.md) con el `Async` modificador. Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>o <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> Un ejemplo más adelante en este tema se muestra un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601>  
  
 `Async``Sub` procedimientos se utilizan principalmente para los controladores de eventos, donde no se puede devolver un valor. Un `Async``Sub` procedimiento no se puede esperar y el llamador de un `Async``Sub` procedimiento no puede detectar las excepciones que la `Sub` procedimiento produce.  
  
 Un `Async` procedimiento no puede declarar ningún [ByRef](../modifiers/byref.md) parámetros.  
  
 Para obtener más información acerca de `Async` procedimientos, consulte [la programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [Async devolver tipos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la `Sub` instrucción para definir el nombre, parámetros y código que forman el cuerpo de un `Sub` procedimiento.  
  
 [!code-vb[VbVbalrStatements&#58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `DelayAsync` es un un `Async``Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`. Dado que el tipo devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un número entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask`.  
  
 El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento. Porque `DoSomethingAsync` es una `Async` (función), la tarea de la llamada a `DoSomethingAsync` debe esperar, tal como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`. El `startButton_Click``Sub` procedimiento debe definirse con la `Async` modificador porque tiene un `Await` expresión.  
  
 [!code-vb[csAsyncMethod n.º&1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](implements-statement.md)   
 [Function (instrucción)](function-statement.md)   
 [Lista de parámetros](parameter-list.md)   
 [Dim (instrucción)](dim-statement.md)   
 [Call (instrucción)](call-statement.md)   
 [Of](of-clause.md)   
 [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Cómo: utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Procedimientos de solución de problemas](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
