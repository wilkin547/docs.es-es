---
title: Sub (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 9a806f2ec979699f7ccf4012c6477bee11301b0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
  
     Opcional. Vea [lista de los atributos](attribute-list.md).  
  
-   `Partial`  
  
     Opcional. Indica la definición de un método parcial. Vea [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Opcional. Puede ser uno de los siguientes:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
     Opcional. Vea [compartido](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Opcional. Vea [sombras](../modifiers/shadows.md).  
  
-   `Async`  
  
     Opcional. Vea [Async](../modifiers/async.md).  
  
-   `name`  
  
     Requerido. Nombre del procedimiento. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento para la `New` palabra clave. Para obtener más información, consulte [duración de los objetos: cómo los objetos son crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Opcional. Lista de parámetros de tipo para un procedimiento genérico. Vea [escriba lista](type-list.md).  
  
-   `parameterlist`  
  
     Opcional. Lista de nombres de variables locales que representan los parámetros de este procedimiento. Vea [lista de parámetros](parameter-list.md).  
  
-   `Implements`  
  
     Opcional. Indica que este procedimiento implementa uno o varios `Sub` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento. Vea [implementa instrucción](implements-statement.md).  
  
-   `implementslist`  
  
     Es necesario si se proporciona `Implements`. Lista de procedimientos `Sub` que se implementan.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:  
  
     `interface.definedname`  
  
    |Parte|Descripción|  
    |---|---|  
    |`interface`|Requerido. Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.|  
    |`definedname`|Requerido. Nombre por el que se define el procedimiento en `interface`.|  
  
-   `Handles`  
  
     Opcional. Indica que este procedimiento puede controlar uno o más eventos específicos. Vea [controla](handles-clause.md).  
  
-   `eventlist`  
  
     Es necesario si se proporciona `Handles`. Lista de eventos que controla este procedimiento.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Cada `eventspecifier` tiene la sintaxis y las partes siguientes:  
  
     `eventvariable.event`  
  
    |Parte|Descripción|  
    |---|---|  
    |`eventvariable`|Requerido. Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.|  
    |`event`|Requerido. Nombre del evento que controla este procedimiento.|  
  
-   `statements`  
  
     Opcional. Bloque de instrucciones que se ejecutan dentro de este procedimiento.  
  
-   `End Sub`  
  
     Termina la definición de este procedimiento.  
  
## <a name="remarks"></a>Comentarios  
 Todo el código ejecutable debe estar dentro de un procedimiento. Use un `Sub` procedimiento si no desea devolver un valor para el código de llamada. Use un `Function` procedimiento cuando desee devolver un valor.  
  
## <a name="defining-a-sub-procedure"></a>Definir un procedimiento Sub  
 Puede definir un `Sub` procedimiento sólo en el nivel de módulo. El contexto de la declaración de un procedimiento sub por lo tanto, debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 `Sub` procedimientos como valor predeterminado para el acceso público. Puede ajustar los niveles de acceso mediante los modificadores de acceso.  
  
 Si el procedimiento utiliza el `Implements` (palabra clave), la clase o estructura contenedora debe tener un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción. El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`. Sin embargo, el nombre por el que una interfaz que define el `Sub` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Devolver desde un procedimiento Sub  
 Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.  
  
 En el ejemplo siguiente se muestra una devolución de un `Sub` procedimiento.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 El `Exit Sub` y `Return` instrucciones provocan una salida inmediata de un `Sub` procedimiento. Cualquier número de `Exit Sub` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Sub` y `Return` las instrucciones.  
  
## <a name="calling-a-sub-procedure"></a>Llamar a un procedimiento Sub  
 Se llama a un `Sub` procedimiento mediante el nombre del procedimiento en una instrucción y, a continuación, siga ese nombre con su lista de argumentos entre paréntesis. Puede omitir los paréntesis solo si no facilita ningún argumento. Sin embargo, el código es más legible si siempre incluye los paréntesis.  
  
 A `Sub` procedimiento y un `Function` procedimiento puede tener parámetros y llevar a cabo una serie de instrucciones. Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` no de procedimiento. Por lo tanto, no puede usar un `Sub` procedimiento en una expresión.  
  
 Puede usar el `Call` palabra clave cuando se llama a un `Sub` procedimiento, pero esa palabra clave no se recomienda para la mayoría de los casos. Para obtener más información, consulte [instrucción Call](call-statement.md).  
  
 Visual Basic reorganiza a veces las expresiones aritméticas para aumentar la eficacia interna. Por esta razón, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que las expresiones se llamará en un orden concreto.  
  
## <a name="async-sub-procedures"></a>Async Sub (procedimientos)  
 Mediante el uso de la característica Async, se pueden invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.  
  
 Si marca un procedimiento con el [Async](../modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el procedimiento. Cuando el control alcanza un `Await` expresión en el `Async` procedimiento, el control vuelve al llamador y el progreso en el procedimiento se suspende hasta que se complete la tarea esperada. Una vez completada la tarea, la ejecución puede reanudarse en el procedimiento.  
  
> [!NOTE]
>  Un `Async` procedimiento vuelve al llamador cuando se encuentra ya sea el primer objeto esperado que aún no se ha completado o el final de la `Async` se alcanza el procedimiento, lo que ocurra primero.  
  
 También puede marcar un [Function (instrucción)](function-statement.md) con el `Async` modificador. Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un ejemplo más adelante en este tema se muestra un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.  
  
 `Async` `Sub` los procedimientos se utilizan principalmente para controladores de eventos, donde no se puede devolver un valor. Un `Async``Sub` procedimiento no se puede esperar y el llamador de un `Async``Sub` procedimiento no puede detectar las excepciones que el `Sub` procedimiento produce.  
  
 Un `Async` procedimiento no puede declarar ningún [ByRef](../modifiers/byref.md) parámetros.  
  
 Para obtener más información acerca de `Async` procedimientos, consulte [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [tipos de valor devueltos de Async](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Sub` instrucción para definir el nombre, parámetros y código que forman el cuerpo de un `Sub` procedimiento.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `DelayAsync` es un `Async``Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>. `DelayAsync` tiene una instrucción `Return` que devuelve un entero. Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`. Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask`.  
  
 El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento. Dado que `DoSomethingAsync` es un `Async` función, la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`. El `startButton_Click``Sub` procedimiento debe definirse con el `Async` modificador porque tiene un `Await` expresión.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](implements-statement.md)  
 [Function (instrucción)](function-statement.md)  
 [Lista de parámetros](parameter-list.md)  
 [Dim (instrucción)](dim-statement.md)  
 [Call (instrucción)](call-statement.md)  
 [Of](of-clause.md)  
 [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Solución de problemas de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
