---
title: "Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Cómo: Declarar una propiedad con niveles de acceso mixtos (Visual Basic)
Si desea que la `Get` y `Set` procedimientos en una propiedad que se va a tener diferentes niveles de acceso, puede utilizar el nivel más permisivo en la `Property` instrucción y el nivel más restrictivo en uno el `Get` o `Set` instrucción. Usar niveles de acceso mixtos en una propiedad cuando desee que ciertas partes del código para que pueda obtener el valor de propiedad y otras partes del código para que pueda cambiar el valor.  
  
 Para obtener más información sobre los niveles de acceso, consulte [tener acceso a niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Para declarar una propiedad con niveles de acceso mixtos  
  
1.  Declare la propiedad de la manera normal y especificar el nivel de acceso menos restrictivo (como `Public`) en el `Property` instrucción.  
  
2.  Declarar cualquiera el `Get` o `Set` procedimiento especificando el nivel de acceso más restrictivo (como `Friend`).  
  
3.  No especifique un nivel de acceso en el procedimiento de la propiedad. Se supone que el nivel de acceso que se declaran en el `Property` instrucción. Puede restringir el acceso solo en uno de los procedimientos de propiedad.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     En el ejemplo anterior, el `Get` procedimiento tiene el mismo `Protected` acceso como la propiedad en Sí, mientras que la `Set` procedimiento tiene `Private` acceso. Una clase derivada de `employee` puede leer el `salary` valor, pero solo el `employee` clase puede establecerlo.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)  
 [Crear una propiedad](./how-to-create-a-property.md)  
 [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)  
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
