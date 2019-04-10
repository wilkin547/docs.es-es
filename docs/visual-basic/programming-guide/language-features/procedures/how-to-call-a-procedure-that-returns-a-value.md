---
title: Filtrar Llamar a un procedimiento que devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333891"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Filtrar Llamar a un procedimiento que devuelve un valor (Visual Basic)
Un `Function` procedimiento devuelve un valor al código de llamada. Llamarlo mediante la inclusión de su nombre y argumentos en el lado derecho de una instrucción de asignación o en una expresión.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Para llamar a un procedimiento Function dentro de una expresión  
  
1. Utilice la `Function` del mismo modo que usaría una variable de nombre de este procedimiento. Puede usar un `Function` llame al procedimiento desde cualquier lugar puede usar una variable o constante en una expresión.  
  
2. Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes.  
  
     Como alternativa, puede pasar uno o más argumentos por nombre. Para obtener más información, consulte [pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md).  
  
4. El valor devuelto del procedimiento participa en la expresión igual que el valor de una variable o constante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Para llamar a un procedimiento Function en una instrucción de asignación  
  
1. Use la `Function` nombre del procedimiento siguiendo la igual (`=`) inicie sesión en la instrucción de asignación.  
  
2. Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes, a menos que se pasan por nombre.  
  
4. El valor devuelto del procedimiento se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> para recuperar el valor de una variable de entorno del sistema operativo. Las llamadas de línea primera `Environ` dentro de una expresión y la segunda línea lo llama en una instrucción de asignación. `Environ` toma el nombre de variable como su único argumento. Devuelve el valor de la variable al código de llamada.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de función](./function-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (Instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Filtrar para crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Filtrar para devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Filtrar apara llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
