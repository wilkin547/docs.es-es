---
title: 'Cómo: Establecer un valor en una propiedad (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00303b290e324612ad3ac7af673690b4cf4e15
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Cómo: Establecer un valor en una propiedad (Visual Basic)
Almacenar un valor en una propiedad colocando el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
 La propiedad `Set` procedimiento almacena un valor, pero no llamar explícitamente a él por su nombre. Use la propiedad tal como utilizaría una variable. Visual Basic realiza las llamadas a procedimientos de la propiedad.  
  
### <a name="to-store-a-value-in-a-property"></a>Para almacenar un valor en una propiedad  
  
1.  Utilice el nombre de propiedad en el lado izquierdo de una instrucción de asignación.  
  
     En el ejemplo siguiente se establece el valor de Visual Basic `TimeOfDay` propiedad al mediodía, se llama implícitamente a su `Set` procedimiento.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Si la propiedad toma argumentos, siga el nombre de propiedad entre paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de que proporcionar los argumentos en el mismo orden que la propiedad define los parámetros correspondientes.  
  
4.  El valor generado en el lado derecho de la instrucción de asignación se almacena en la propiedad.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)  
 [Crear una propiedad](./how-to-create-a-property.md)  
 [Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
