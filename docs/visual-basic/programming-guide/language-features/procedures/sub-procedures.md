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
ms.openlocfilehash: 646d7d217891dc8ea5b78f7ce30fce19fab08316
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977583"
---
# <a name="sub-procedures-visual-basic"></a>Subprocedimientos (Visual Basic)
Un `Sub` procedimiento es una serie de instrucciones de Visual Basic está incluido en el `Sub` y `End Sub` instrucciones. El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.  
  
 Cada vez que se llama al procedimiento, se ejecutan las instrucciones, empezando por la primera instrucción ejecutable tras el `Sub` instrucción y terminando por la primera `End Sub`, `Exit Sub`, o `Return` encontrada una instrucción.  
  
 Puede definir un `Sub` procedimiento en módulos, clases y estructuras. De forma predeterminada, es `Public`, lo que significa que puede llamar desde cualquier lugar en la aplicación que tiene acceso al módulo, clase o estructura en el que se define. El término, *método*, describe un `Sub` o `Function` procedimiento que se obtiene acceso desde fuera de su definición de módulo, clase o estructura. Para más información, vea [Procedimientos en Visual Basic](./index.md).  
  
 Un `Sub` procedimiento puede tomar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Sub` es el procedimiento siguiente:  
  
 `[` *modificadores* `] Sub` *subname* `[(` *parameterlist* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 El `modifiers` puede especificar el nivel de acceso e información sobre la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Declaración de parámetros  
 Declarar cada parámetro de procedimiento de forma similar a cómo declarar una variable, especificando el tipo de datos y el nombre de parámetro. También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.  
  
 La sintaxis para cada parámetro en la lista de parámetros es como sigue:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*datatype*  
  
 Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es como sigue:  
  
 `Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*  
  
### <a name="parameters-as-local-variables"></a>Parámetros como Variables locales  
 Cuando el control pasa al procedimiento, cada parámetro se tratan como una variable local. Esto significa que su duración es igual que el del procedimiento y su ámbito es el procedimiento completo.  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Se invoca un `Sub` procedimiento explícitamente con una instrucción de llamada independiente. No se puede llamar a utilizando su nombre en una expresión. Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis. Si se proporciona ningún argumento, opcionalmente, puede omitir los paréntesis. El uso de la `Call` palabra clave es opcional, pero no se recomienda.  
  
 La sintaxis para llamar a un `Sub` es el procedimiento siguiente:  
  
 `[Call]`  *subname* `[(` *argumentlist* `)]`  
  
 Puede llamar a un `Sub` método desde fuera de la clase que lo define. En primer lugar, tiene que usar el `New` palabra clave para crear una instancia de la clase o llamar a un método que devuelve una instancia de la clase. Para obtener más información, consulte [nuevo operador](../../../../visual-basic/language-reference/operators/new-operator.md). A continuación, puede usar la siguiente sintaxis para llamar a la `Sub` método en el objeto de instancia:  
  
 *Objeto*. *MethodName*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Ilustración de la declaración y llamada  
 La siguiente `Sub` procedimiento le indica al usuario del equipo tarea que la aplicación está a punto de llevar a cabo y también muestra una marca de tiempo. En lugar de duplicar este código al principio de cada tarea, la aplicación simplemente llama a `tellOperator` desde varias ubicaciones. Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se está iniciando.  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 El ejemplo siguiente muestra una llamada típica al `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Cómo: Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Cómo: Llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
