---
title: 'Cómo: Declarar una propiedad con niveles de acceso mixtos'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349695"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)
Si desea que los procedimientos `Get` y `Set` de una propiedad tengan niveles de acceso diferentes, puede usar el nivel más permisivo en la instrucción `Property` y el nivel más restrictivo en la instrucción `Get` o `Set`. Puede usar niveles de acceso mixtos en una propiedad si desea que determinadas partes del código puedan obtener el valor de la propiedad y otras partes del código para poder cambiar el valor.  
  
 Para obtener más información sobre los niveles de acceso, vea [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Para declarar una propiedad con niveles de acceso mixtos  
  
1. Declare la propiedad de la manera normal y especifique el nivel de acceso menos restrictivo (como `Public`) en la instrucción `Property`.  
  
2. Declare el `Get` o el procedimiento `Set` especificando el nivel de acceso más restrictivo (como `Friend`).  
  
3. No especifique un nivel de acceso en el otro procedimiento de propiedad. Se asume el nivel de acceso declarado en la instrucción `Property`. Puede restringir el acceso solo en uno de los procedimientos de propiedad.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     En el ejemplo anterior, el procedimiento `Get` tiene el mismo acceso `Protected` que la propiedad, mientras que el procedimiento `Set` tiene `Private` acceso. Una clase derivada de `employee` puede leer el valor de `salary`, pero solo la clase `employee` puede establecerlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Crear una propiedad](./how-to-create-a-property.md)
- [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
