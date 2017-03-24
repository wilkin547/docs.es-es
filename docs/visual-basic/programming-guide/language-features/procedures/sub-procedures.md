---
title: Sub (procedimientos) (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
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
ms.openlocfilehash: d224fa3338ca707070ee431380578a8fdde47e07
ms.lasthandoff: 03/13/2017

---
# <a name="sub-procedures-visual-basic"></a>Subprocedimientos (Visual Basic)
Un `Sub` procedimiento es una serie de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] instrucciones delimitadas por la `Sub` y `End Sub` instrucciones. El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.  
  
 Cada vez que se llama al procedimiento, se ejecutan las instrucciones, a partir de la primera instrucción ejecutable tras la `Sub` instrucción y terminando por la primera `End Sub`, `Exit Sub`, o `Return` instrucción que se encuentre.  
  
 Puede definir un `Sub` procedimiento en módulos, clases y estructuras. De forma predeterminada, es `Public`, lo que significa que puede llamar desde cualquier lugar en la aplicación que tiene acceso el módulo, clase o estructura en el que se ha definido. El término *método*, describe un `Sub` o `Function` procedimiento que se tiene acceso desde fuera de su definición de módulo, clase o estructura. Para obtener más información, consulte [procedimientos](./index.md).  
  
 Un `Sub` procedimiento puede tomar argumentos, como constantes, variables o expresiones, que le pasa el código de llamada.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un `Sub` procedimiento es el siguiente:  
  
 `[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 La `modifiers` puede especificar el nivel de acceso e información acerca de la sobrecarga, invalidación, uso compartido y sombreado. Para obtener más información, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Declaración de parámetros  
 Declarar el parámetro del procedimiento de forma similar a cómo declarar una variable, especificando el tipo de datos y el nombre de parámetro. También puede especificar el mecanismo para pasar argumentos y si el parámetro es opcional o una matriz de parámetros.  
  
 La sintaxis para cada parámetro en la lista de parámetros es como sigue:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*tipo de datos    *  
  
 Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es el siguiente:  
  
 `Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue        *  
  
### <a name="parameters-as-local-variables"></a>Parámetros como Variables locales  
 Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local. Esto significa que su duración es igual que el del procedimiento y su ámbito es el procedimiento completo.  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Invocar un `Sub` procedimiento explícitamente con una instrucción de llamada independiente. No se puede llamar utilizando su nombre en una expresión. Debe proporcionar valores para todos los argumentos que no sean opcionales, y debe incluir la lista de argumentos entre paréntesis. Si no se proporcionan argumentos, se pueden omitir los paréntesis. El uso de la `Call` palabra clave es opcional, pero no se recomienda.  
  
 La sintaxis para llamar a un `Sub` procedimiento es el siguiente:  
  
 `[Call]`  *nombre secundario* `[(` *argumentlist*`)]`  
  
 Puede llamar a un `Sub` método desde fuera de la clase que lo define. En primer lugar, tiene que usar el `New` (palabra clave) para crear una instancia de la clase o llamar a un método que devuelve una instancia de la clase. Para obtener más información, consulte [nuevo operador](../../../../visual-basic/language-reference/operators/new-operator.md). A continuación, puede utilizar la siguiente sintaxis para llamar a la `Sub` en el objeto de instancia:  
  
 *Object*.* MethodName*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Ejemplo de declaración y llamada  
 La siguiente `Sub` procedimiento explica el usuario del equipo la tarea que la aplicación está a punto de realizar y también muestra una marca de tiempo. En lugar de duplicar este código al principio de cada tarea, la aplicación simplemente llama a `tellOperator` desde varias ubicaciones. Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se va a iniciar.  
  
 [!code-vb[VbVbcnProcedures&#2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures&3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Cómo: llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
