---
title: 'Cómo: Llamar a un procedimiento de propiedad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 61d79b9ff99ec144a9c629872abd2a7e7ebda4d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de propiedad (Visual Basic)
Puede llamar a un procedimiento de propiedad almacena un valor en la propiedad o recuperar su valor. Tener acceso a una propiedad de la misma manera que se obtenga acceso a una variable.  
  
 La propiedad `Set` procedimiento almacena un valor y su `Get` procedimiento recupera el valor. Sin embargo, no llame explícitamente estos procedimientos por su nombre. Use la propiedad en una instrucción de asignación o una expresión, tal y como haría almacenar o recuperar el valor de una variable. Visual Basic realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Para llamar al procedimiento de Get de una propiedad  
  
1.  Utilice el nombre de propiedad en una expresión de la misma manera que usaría un nombre de variable. Puede usar una propiedad en cualquier lugar puede usar una variable o una constante.  
  
     -o bien-  
  
     Utilice el nombre de la propiedad siguiendo la igual (`=`) iniciar sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> propiedad, se llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión al igual que una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Para llamar a una propiedad de conjunto del procedimiento  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> propiedad, se llama implícitamente a la `Set` procedimiento.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)  
 [Crear una propiedad](./how-to-create-a-property.md)  
 [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)  
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)  
 [Get (instrucción)](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set (instrucción)](../../../../visual-basic/language-reference/statements/set-statement.md)
