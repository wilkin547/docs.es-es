---
title: Filtrar Establecer un valor en una propiedad (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ee2449ff905bfdacaeeee4cc244db1ce50e00104
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824316"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Filtrar Establecer un valor en una propiedad (Visual Basic)
Almacenar un valor en una propiedad colocando el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
 La propiedad `Set` procedimiento almacena un valor, pero no llamar explícitamente a él por su nombre. Use la propiedad igual que usaría una variable. Visual Basic realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-store-a-value-in-a-property"></a>Para almacenar un valor en una propiedad  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de Visual Basic `TimeOfDay` propiedad a mediodía, se llama implícitamente a su `Set` procedimiento.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
4.  El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Cómo: Crear una propiedad](./how-to-create-a-property.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Cómo: Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Cómo: Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
