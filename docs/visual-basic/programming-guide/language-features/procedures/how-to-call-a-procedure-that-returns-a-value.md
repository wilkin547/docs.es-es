---
title: 'Cómo: Llamar a un procedimiento que devuelve un valor (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 35f757609b6d0b36652db3b14e62ecd299a063ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que devuelve un valor (Visual Basic)
A `Function` procedimiento devuelve un valor para el código de llamada. Se llama mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Llamar a un procedimiento de función dentro de una expresión  
  
1.  Utilice la `Function` del mismo modo que usaría una variable de nombre de este procedimiento. Puede usar un `Function` llamada a procedimiento desde cualquier lugar puede usar una variable o constante en una expresión.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis, el código será más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes.  
  
     Como alternativa, puede pasar uno o más argumentos por nombre. Para obtener más información, consulte [pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md).  
  
4.  El valor devuelto desde el procedimiento participa en la expresión al igual que el valor de una variable o constante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Llamar a un procedimiento de función en una instrucción de asignación  
  
1.  Use la `Function` nombre del procedimiento siguiente iguales (`=`) iniciar sesión en la instrucción de asignación.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis, el código será más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes, a menos que se están pasando por su nombre.  
  
4.  El valor devuelto del procedimiento se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se llama Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> para recuperar el valor de una variable de entorno de sistema operativo. Las llamadas de línea primera `Environ` dentro de una expresión y la segunda línea llama en una instrucción de asignación. `Environ` toma el nombre de variable como su único argumento. Devuelve el valor de la variable en el código que realiza la llamada.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de función](./function-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)  
 [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
