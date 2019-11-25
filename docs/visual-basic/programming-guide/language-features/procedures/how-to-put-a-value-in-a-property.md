---
title: 'Cómo: Establecer un valor en una propiedad'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ad0d0e81f94dd3dead50f21c3bd6ff580c004dd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346052"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Cómo: Establecer un valor en una propiedad (Visual Basic)
You store a value in a property by putting the property name on the left side of an assignment statement.  
  
 The property's `Set` procedure stores a value, but you do not explicitly call it by name. You use the property just as you would use a variable. Visual Basic makes the calls to the property's procedures.  
  
### <a name="to-store-a-value-in-a-property"></a>To store a value in a property  
  
1. Use the property name on the left side of an assignment statement.  
  
     The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. If the property takes arguments, follow the property name with parentheses to enclose the argument list. If there are no arguments, you can optionally omit the parentheses.  
  
3. Place the arguments in the argument list within the parentheses, separated by commas. Be sure you supply the arguments in the same order that the property defines the corresponding parameters.  
  
4. The value generated on the right side of the assignment statement is stored in the property.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md)
- [Crear una propiedad](./how-to-create-a-property.md)
- [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
