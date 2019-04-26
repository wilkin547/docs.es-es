---
title: Procedimiento Obtener un valor de una propiedad (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5e2676a0880092a78405fe5dafa0469161b85610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863641"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Procedimiento Obtener un valor de una propiedad (Visual Basic)
Para recuperar un valor de propiedad, incluido el nombre de propiedad en una expresión.  
  
 La propiedad `Get` procedimiento recupera el valor, pero no llamar explícitamente a él por su nombre. Use la propiedad igual que usaría una variable. Visual Basic realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Para recuperar un valor de una propiedad  
  
1. Utilice el nombre de propiedad en una expresión de la misma manera que utilizaría un nombre de variable. Puede usar una propiedad en cualquier lugar puede usar una variable o una constante.  
  
     -o bien-  
  
     Utilice el nombre de propiedad tras la igual (`=`) inicie sesión en una instrucción de asignación.  
  
     El ejemplo siguiente lee el valor de Visual Basic `Now` propiedad, se llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión igual que una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Cómo: Crear una propiedad](./how-to-create-a-property.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Cómo: Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Cómo: Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
