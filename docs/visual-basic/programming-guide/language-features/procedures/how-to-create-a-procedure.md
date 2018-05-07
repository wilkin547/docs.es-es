---
title: 'Cómo: Crear un procedimiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: da4cc299fbe35702990a62b5bf824e3ac71d5902
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Cómo: Crear un procedimiento (Visual Basic)
Incluir un procedimiento entre una instrucción de declaración inicial (`Sub` o `Function`) y una instrucción de declaración final (`End Sub` o `End Function`). Todo el código de procedimiento está comprendida entre estas instrucciones.  
  
 Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones inicial y finales deben estar fuera de cualquier otro procedimiento.  
  
 Si tiene código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez que un procedimiento y, a continuación, llamarlo desde distintos lugares del código.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Para crear un procedimiento que no devuelve un valor  
  
1.  Fuera de cualquier otro procedimiento, utilice un `Sub` instrucción, seguida de un `End Sub` instrucción.  
  
2.  En el `Sub` (instrucción), siga el `Sub` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3.  Coloque las instrucciones de código del procedimiento entre el `Sub` y `End Sub` las instrucciones.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor  
  
1.  Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.  
  
2.  En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis y, a continuación, un `As` cláusula que especifica el tipo de datos del valor devuelto.  
  
3.  Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` las instrucciones.  
  
4.  Use un `Return` instrucción para devolver el valor para el código de llamada.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Para conectar el nuevo procedimiento con los bloques anteriores y repetitivos de código  
  
1.  Asegúrese de que define el nuevo procedimiento en un lugar donde el código anterior tiene acceso a él.  
  
2.  En el bloque de código anterior, repetitivos, reemplace las instrucciones que realizan la tarea repetitiva con una sola instrucción que llama el `Sub` o `Function` procedimiento.  
  
3.  Si el procedimiento es un `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como el almacenamiento en una variable, o bien el valor se perderá.  
  
## <a name="example"></a>Ejemplo  
 El siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los otros dos lados.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>Vea también

 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Procedimientos recursivos](./recursive-procedures.md)  
 [Sobrecarga de procedimientos](./procedure-overloading.md)  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)  
