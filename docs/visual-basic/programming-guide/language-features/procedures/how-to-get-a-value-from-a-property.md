---
title: "Cómo: obtener un valor de una propiedad (Visual Basic) | Documentos de Microsoft"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 7487e4cde724c46a193639f2ad116d25e4ff834c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Cómo: Obtener un valor de una propiedad (Visual Basic)
Recupera el valor de una propiedad incluyendo el nombre de propiedad en una expresión.  
  
 La propiedad `Get` procedimiento recupera el valor, pero no llamarlo explícitamente por nombre. Utilice la propiedad tal como utilizaría una variable. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Para recuperar un valor de una propiedad  
  
1.  Utilice el nombre de propiedad en una expresión del mismo modo que utilizaría un nombre de variable. Puede utilizar una propiedad en cualquier lugar puede utilizar una variable o una constante.  
  
     O bien  
  
     Utilice el nombre de propiedad sigue igual (`=`) inicie sesión en una instrucción de asignación.  
  
     En el ejemplo siguiente se lee el valor de la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` propiedad, se llama implícitamente a su `Get` procedimiento.  
  
     [!code-vb[VbVbalrDateProperties Nº&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, se pueden omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
 El valor de la propiedad participa en la expresión como una variable o constante, o se almacena en la variable o propiedad en el lado izquierdo de la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)   
 [Cómo: crear una propiedad](./how-to-create-a-property.md)   
 [Cómo: declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)   
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
