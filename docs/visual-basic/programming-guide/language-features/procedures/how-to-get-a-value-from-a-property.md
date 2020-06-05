---
title: Procedimiento para obtener un valor de una propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 2c92cd4a869acbb7c8c52fbf4117112967386498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387899"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Cómo: Obtener un valor de una propiedad (Visual Basic)
Para recuperar el valor de una propiedad, incluya el nombre de la propiedad en una expresión.  
  
 El procedimiento de la propiedad `Get` recupera el valor, pero no lo llama explícitamente por su nombre. La propiedad se usa de la misma manera que se usaría una variable. Visual Basic realiza las llamadas a los procedimientos de la propiedad.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Para recuperar un valor de una propiedad  
  
1. Use el nombre de la propiedad en una expresión de la misma manera que usaría un nombre de variable. Puede usar una propiedad en cualquier lugar en el que pueda usar una variable o una constante.  
  
     O bien  
  
     Use el nombre de la propiedad que sigue al signo igual ( `=` ) en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la `Now` propiedad Visual Basic, que llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Si la propiedad toma argumentos, siga el nombre de la propiedad entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión como una variable o una constante, o se almacena en la variable o la propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Procedimiento para crear una propiedad](./how-to-create-a-property.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedimiento para llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedimiento para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
