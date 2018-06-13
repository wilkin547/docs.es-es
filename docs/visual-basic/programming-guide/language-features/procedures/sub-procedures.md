---
title: Subprocedimientos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 3286df1a5babfcf7d6b759ff5c9a920bb44f51ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652570"
---
# <a name="sub-procedures-visual-basic"></a>Subprocedimientos (Visual Basic)
A `Sub` procedimiento es una serie de instrucciones de Visual Basic delimitadas por la `Sub` y `End Sub` las instrucciones. El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor para el código de llamada.  
  
 Cada vez que se llama al procedimiento, se ejecutan las instrucciones, a partir de la primera instrucción ejecutable tras la `Sub` instrucción y terminando con la primera `End Sub`, `Exit Sub`, o `Return` encontrada una instrucción.  
  
 Puede definir un `Sub` procedimiento en módulos, clases y estructuras. De forma predeterminada, es `Public`, lo cual significa que puede llamar desde cualquier lugar en la aplicación que tiene acceso el módulo, clase o estructura en el que se ha definido. El término, *método*, describe un `Sub` o `Function` procedimiento que se obtiene acceso desde fuera de su definición de módulo, clase o estructura. Para más información, vea [Procedimientos en Visual Basic](./index.md).  
  
 A `Sub` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Sub` procedimiento es el siguiente:  
  
 `[` *modificadores* `] Sub` *nombre secundario* `[(` *parameterlist* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 La `modifiers` puede especificar un nivel de acceso e información acerca de la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Declaración de parámetro  
 Declarar cada parámetro de procedimiento de forma similar a cómo se declara una variable, especificando el tipo de datos y el nombre de parámetro. También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.  
  
 La sintaxis para cada parámetro en la lista de parámetros es como sigue:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*tipo de datos*  
  
 Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es como sigue:  
  
 `Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*  
  
### <a name="parameters-as-local-variables"></a>Parámetros como Variables locales  
 Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local. Esto significa que su duración es igual que la del procedimiento y su ámbito es el procedimiento completo.  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Se invoca un `Sub` procedimiento explícitamente con una instrucción llamada independiente. No se puede llamar a mediante su nombre en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis. Si no se proporcionan argumentos, se pueden omitir los paréntesis. El uso de la `Call` palabra clave es opcional, pero no se recomienda.  
  
 La sintaxis de una llamada a un `Sub` procedimiento es el siguiente:  
  
 `[Call]`  *nombre secundario* `[(` *argumentlist* `)]`  
  
 Puede llamar a un `Sub` método desde fuera de la clase que lo define. En primer lugar, tiene que utilizar el `New` palabra clave se debe crear una instancia de la clase o llamar a un método que devuelve una instancia de la clase. Para obtener más información, consulte [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md). A continuación, puede utilizar la siguiente sintaxis para llamar a la `Sub` método en el objeto de instancia:  
  
 *Objeto*. *MethodName*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaración y llamada  
 El siguiente `Sub` procedimiento explica el usuario del equipo la tarea que la aplicación está a punto de realizar y también muestra una marca de tiempo. En lugar de duplicar este código al principio de cada tarea, la aplicación simplemente llama `tellOperator` desde diversas ubicaciones. Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se va a iniciar.  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
