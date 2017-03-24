---
title: "Cómo: llamar a un procedimiento de propiedad (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7dd3d53f602886f65c951de34b915b2672b1a817
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de propiedad (Visual Basic)
Puede llamar a un procedimiento de propiedad almacena un valor en la propiedad o recuperar su valor. Obtener acceso a una propiedad del mismo modo que se obtiene acceso a una variable.  
  
 La propiedad `Set` procedimiento almacena un valor y su `Get` procedimiento recupera el valor. Sin embargo, no llame explícitamente estos procedimientos por nombre. Utilice la propiedad en una instrucción de asignación o una expresión, tal y como podría almacenar o recuperar el valor de una variable. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Para llamar a un procedimiento de Get  
  
1.  Utilice el nombre de propiedad en una expresión del mismo modo que utilizaría un nombre de variable. Puede utilizar una propiedad en cualquier lugar puede utilizar una variable o una constante.  
  
     O bien  
  
     Utilice el nombre de propiedad sigue igual (`=`) inicie sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>propiedad, se llama implícitamente a su `Get` procedimiento.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
  
     [!code-vb[VbVbalrDateProperties Nº&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión como una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Para llamar a una propiedad de conjunto del procedimiento  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de la <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>propiedad, se llama implícitamente a la `Set` procedimiento.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
  
     [!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Property (procedimientos)](./property-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)   
 [Cómo: crear una propiedad](./how-to-create-a-property.md)   
 [Cómo: declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Cómo: establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)   
 [Cómo: obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)   
 [Get (instrucción)](../../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set (instrucción)](../../../../visual-basic/language-reference/statements/set-statement.md)
