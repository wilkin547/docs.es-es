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
Para almacenar un valor en una propiedad, coloque el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.  
  
 El procedimiento `Set` de la propiedad almacena un valor, pero no lo llama explícitamente por su nombre. La propiedad se usa de la misma manera que se usaría una variable. Visual Basic realiza las llamadas a los procedimientos de la propiedad.  
  
### <a name="to-store-a-value-in-a-property"></a>Para almacenar un valor en una propiedad  
  
1. Use el nombre de la propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la propiedad Visual Basic `TimeOfDay` en mediodía, llamando implícitamente a su procedimiento `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
4. El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Crear una propiedad](./how-to-create-a-property.md)
- [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
