---
title: "Cómo: llamar a un procedimiento que devuelve un valor (Visual Basic) | Documentos de Microsoft"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: df6bb1ed8acf5f86a290d67fec9c053cfe5245d2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que devuelve un valor (Visual Basic)
Un `Function` procedimiento devuelve un valor al código de llamada. Llama a, incluyendo el nombre y los argumentos en el lado derecho de una instrucción de asignación o en una expresión.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>Llamar a un procedimiento de función dentro de una expresión  
  
1.  Utilice la `Function` del mismo modo que utilizaría una variable de nombre de este procedimiento. Puede usar un `Function` desde cualquier lugar puede utilizar una variable o constante en una expresión de llamada a procedimiento.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis. Sin embargo, los paréntesis hacen el código más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes.  
  
     Como alternativa, puede pasar uno o varios argumentos por nombre. Para obtener más información, consulte [pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md).  
  
4.  El valor devuelto desde el procedimiento participa en la expresión de valor de una variable o constante.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>Para llamar a un procedimiento Function en una instrucción de asignación  
  
1.  Utilice la `Function` nombre del procedimiento siguiente iguales (`=`) inicie sesión en la instrucción de asignación.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis. Sin embargo, los paréntesis hacen el código más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Function` procedimiento define los parámetros correspondientes, a menos que se pasan por nombre.  
  
4.  El valor devuelto del procedimiento se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se llama el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>para recuperar el valor de una variable de entorno del sistema operativo.</xref:Microsoft.VisualBasic.Interaction.Environ%2A> La primera línea las llamadas `Environ` dentro de una expresión y la segunda línea hace la llamada en una instrucción de asignación. `Environ`toma el nombre de variable como único argumento. Devuelve el valor de la variable al código de llamada.  
  
 [!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Function (procedimientos)](./function-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Cómo: crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Cómo: devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)   
 [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
