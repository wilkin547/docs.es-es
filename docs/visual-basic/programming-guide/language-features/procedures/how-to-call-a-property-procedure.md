---
description: 'Más información acerca de cómo: llamar a un procedimiento de propiedad (Visual Basic)'
title: Procedimiento para llamar a un procedimiento de propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 541768cb6381aa3d2b1bf75267c5b34a82a3d2ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466762"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de propiedad (Visual Basic)

Para llamar a un procedimiento de propiedad, se almacena un valor en la propiedad o se recupera su valor. Puede tener acceso a una propiedad de la misma manera que tiene acceso a una variable.  
  
 El procedimiento de la propiedad `Set` almacena un valor y su `Get` procedimiento recupera el valor. Sin embargo, no se llama a estos procedimientos explícitamente por nombre. La propiedad se usa en una instrucción de asignación o una expresión, tal como se almacenaría o recuperaría el valor de una variable. Visual Basic realiza las llamadas a los procedimientos de la propiedad.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Para llamar al procedimiento get de una propiedad  
  
1. Use el nombre de la propiedad en una expresión de la misma manera que usaría un nombre de variable. Puede usar una propiedad en cualquier lugar en el que pueda usar una variable o una constante.  
  
     o bien  
  
     Use el nombre de la propiedad que sigue al signo igual ( `=` ) en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> propiedad, que llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión como una variable o una constante, o se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Para llamar al procedimiento set de una propiedad  
  
1. Use el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> propiedad, que llama implícitamente al `Set` procedimiento.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Procedimiento para crear una propiedad](./how-to-create-a-property.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedimiento para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Procedimiento para obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
- [Get (Instrucción)](../../../language-reference/statements/get-statement.md)
- [Set (instrucción)](../../../language-reference/statements/set-statement.md)
