---
title: Procedimiento para llamar a un procedimiento que devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 53589f84c6675d1e7ae2a593341e5dac747132a9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083982"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que devuelve un valor (Visual Basic)

Un `Function` procedimiento devuelve un valor al código de llamada. Para llamarlo, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Para llamar a un procedimiento de función dentro de una expresión  
  
1. Use el `Function` nombre del procedimiento del mismo modo que usaría una variable. Puede usar una `Function` llamada a procedimiento en cualquier lugar en el que pueda usar una variable o una constante en una expresión.  
  
2. Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente. Sin embargo, el uso de los paréntesis facilita la lectura del código.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que el `Function` procedimiento define los parámetros correspondientes.  
  
     Como alternativa, puede pasar uno o varios argumentos por nombre. Para obtener más información, vea [pasar argumentos por posición y por nombre](./passing-arguments-by-position-and-by-name.md).  
  
4. El valor devuelto del procedimiento participa en la expresión de la misma forma que el valor de una variable o constante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Para llamar a un procedimiento de función en una instrucción de asignación  
  
1. Use el `Function` nombre del procedimiento que sigue al `=` signo igual () en la instrucción de asignación.  
  
2. Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente. Sin embargo, el uso de los paréntesis facilita la lectura del código.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que el `Function` procedimiento define los parámetros correspondientes, a menos que los pase por nombre.  
  
4. El valor devuelto del procedimiento se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se llama al Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> para recuperar el valor de una variable de entorno del sistema operativo. La primera línea llama a `Environ` dentro de una expresión y la segunda línea la llama en una instrucción de asignación. `Environ` toma el nombre de la variable como su único argumento. Devuelve el valor de la variable al código de llamada.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de función](./function-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Function](../../../language-reference/statements/function-statement.md)
- [Procedimiento para crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedimiento para devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Procedimiento apara llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
