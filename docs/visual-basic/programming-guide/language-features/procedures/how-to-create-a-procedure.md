---
title: Procedimiento Crear un procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665811"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedimiento Crear un procedimiento (Visual Basic)
Incluya un procedimiento entre una instrucción de declaración inicial (`Sub` o `Function`) y una instrucción de declaración final (`End Sub` o `End Function`). Todo el código de procedimiento está comprendida entre estas instrucciones.  
  
 Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones inicial y finales deben ser fuera de cualquier otro procedimiento.  
  
 Si tiene código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez que un procedimiento y, a continuación, llamarlo desde distintos lugares del código.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Para crear un procedimiento que no devuelve un valor  
  
1. Fuera de cualquier otro procedimiento, utilice un `Sub` instrucción, seguida de un `End Sub` instrucción.  
  
2. En el `Sub` (instrucción), siga el `Sub` palabra clave con el nombre del procedimiento y, después, en la lista de parámetros entre paréntesis.  
  
3. Coloque las instrucciones de código del procedimiento entre el `Sub` y `End Sub` instrucciones.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor  
  
1. Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.  
  
2. En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, después, en la lista de parámetros entre paréntesis y, a continuación, un `As` cláusula que especifica el tipo de datos del valor devuelto.  
  
3. Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` instrucciones.  
  
4. Use un `Return` instrucción para devolver el valor al código de llamada.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Para conectar el nuevo procedimiento con los bloques de código anteriores, repetitivos  
  
1. Asegúrese de que define el nuevo procedimiento en un lugar donde el código anterior tiene acceso a él.  
  
2. En el bloque de código anterior y repetitivas, reemplace las instrucciones que realizan las tareas repetitivas con una sola instrucción que llama a la `Sub` o `Function` procedimiento.  
  
3. Si el procedimiento es un `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como almacenarlo en una variable, o bien el valor se perderá.  
  
## <a name="example"></a>Ejemplo  
 La siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los dos lados.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
