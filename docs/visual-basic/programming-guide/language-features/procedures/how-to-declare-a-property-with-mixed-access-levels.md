---
title: Procedimiento para declarar una propiedad con niveles de acceso mixtos
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
ms.openlocfilehash: 78363f7b2fb5b251f7409e53b2802baf83b05810
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072709"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)

Si desea que los `Get` `Set` procedimientos y de una propiedad tengan niveles de acceso diferentes, puede usar el nivel más permisivo en la `Property` instrucción y el nivel más restrictivo en la `Get` `Set` instrucción o. Puede usar niveles de acceso mixtos en una propiedad si desea que determinadas partes del código puedan obtener el valor de la propiedad y otras partes del código para poder cambiar el valor.  
  
 Para obtener más información sobre los niveles de acceso, vea [niveles de acceso en Visual Basic](../declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Para declarar una propiedad con niveles de acceso mixtos  
  
1. Declare la propiedad de la manera normal y especifique el nivel de acceso menos restrictivo (como `Public` ) en la `Property` instrucción.  
  
2. Declare `Get` o el `Set` procedimiento que especifica el nivel de acceso más restrictivo (como `Friend` ).  
  
3. No especifique un nivel de acceso en el otro procedimiento de propiedad. Se asume el nivel de acceso declarado en la `Property` instrucción. Puede restringir el acceso solo en uno de los procedimientos de propiedad.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     En el ejemplo anterior, el `Get` procedimiento tiene el mismo `Protected` acceso que la propiedad, mientras que el `Set` procedimiento tiene `Private` acceso. Una clase derivada de `employee` puede leer el `salary` valor, pero solo la `employee` clase puede establecerlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Procedimiento para crear una propiedad](./how-to-create-a-property.md)
- [Procedimiento para llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedimiento para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Procedimiento para obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
