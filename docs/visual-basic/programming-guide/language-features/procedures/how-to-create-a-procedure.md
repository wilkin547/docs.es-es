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
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216725"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>Procedimiento Crear un procedimiento (Visual Basic)

Puede incluir un procedimiento entre una instrucción de declaración de`Sub` Inicio `Function`(o) y una instrucción de`End Sub` declaración `End Function`de finalización (o). Todo el código del procedimiento se encuentra entre estas instrucciones.

 Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones de inicio y finalización deben estar fuera de cualquier otro procedimiento.

 Si tiene código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez como un procedimiento y, a continuación, llamarla desde distintos lugares del código.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>Para crear un procedimiento que no devuelve un valor

1. Fuera de cualquier otro procedimiento, use `Sub` una instrucción seguida de una `End Sub` instrucción.

2. En la `Sub` instrucción, siga la `Sub` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.

3. Coloque las instrucciones de código del procedimiento entre `Sub` las `End Sub` instrucciones y.

### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor

1. Fuera de cualquier otro procedimiento, use `Function` una instrucción seguida de una `End Function` instrucción.

2. En la `Function` instrucción, siga la `Function` palabra clave con el nombre del procedimiento, la lista de parámetros entre paréntesis y, a continuación, `As` una cláusula que especifique el tipo de datos del valor devuelto.

3. Coloque las instrucciones de código del procedimiento entre `Function` las `End Function` instrucciones y.

4. Use una `Return` instrucción para devolver el valor al código de llamada.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>Para conectar el nuevo procedimiento con los bloques de código repetitivos anteriores

1. Asegúrese de definir el nuevo procedimiento en un lugar donde el código anterior tenga acceso a él.

2. En el bloque de código anterior, repetitivo, reemplace las instrucciones que realizan la tarea repetitiva con una única instrucción que `Sub` llama `Function` al procedimiento o.

3. Si el procedimiento es un `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como el almacenamiento en una variable, o bien se perderá el valor.

## <a name="example"></a>Ejemplo

 En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados:

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>Vea también

- [Procedimientos](index.md)
- [Subprocedimientos](sub-procedures.md)
- [Procedimientos de función](function-procedures.md)
- [Procedimientos de propiedades](property-procedures.md)
- [Procedimientos de operadores](operator-procedures.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Procedimientos recursivos](recursive-procedures.md)
- [Sobrecarga de procedimientos](procedure-overloading.md)
- [Objetos y clases](../objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
