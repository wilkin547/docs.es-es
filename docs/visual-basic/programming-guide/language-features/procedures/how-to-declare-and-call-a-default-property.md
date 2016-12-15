---
title: "C&#243;mo: Declarar y llamar a una propiedad predeterminada en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedades predeterminadas"
  - "propiedades predeterminadas, en Visual Basic"
  - "predeterminados, propiedades"
  - "procedimientos, definir"
  - "propiedades [Visual Basic], predeterminado"
  - "código de Visual Basic, procedimientos"
  - "código de Visual Basic, propiedades"
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Declarar y llamar a una propiedad predeterminada en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *propiedad predeterminada* es una propiedad de clase o de estructura a la que el código puede tener acceso sin especificarlo.  Cuando el código de llamada menciona una clase o estructura pero no una propiedad, y el contexto permite tener acceso a una propiedad, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resuelve el acceso a la propiedad predeterminada de esa clase o estructura, si existe.  
  
 Una clase o estructura puede tener a lo sumo una propiedad predeterminada.  No obstante, puede sobrecargar una propiedad predeterminada y tener más de una versión de ella.  
  
 Para obtener más información, vea [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### Para declarar una propiedad predeterminada  
  
1.  Declare la propiedad de la manera normal.  No especifique la palabra clave `Shared` o `Private`.  
  
2.  Incluya la palabra clave `Default` en la declaración de la propiedad.  
  
3.  Especifique al menos un parámetro para la propiedad.  No puede definir una propiedad predeterminada que no acepte al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#17](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### Para llamar a una propiedad predeterminada  
  
1.  Declare una variable de la clase contenedora o tipo de estructura.  
  
     [!code-vb[VbVbcnProcedures#16](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Utilice el nombre de variable solo en una expresión donde normalmente incluiría el nombre de propiedad.  
  
     [!code-vb[VbVbcnProcedures#21](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Agregue detrás del nombre de variable una lista de argumentos entre paréntesis.  Una propiedad predeterminada debe aceptar al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#20](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Para recuperar el valor de propiedad predeterminado, utilice el nombre de variable, con una lista de argumentos, en una expresión o detrás del signo igual \(`=`\) en una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#15](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Para establecer el valor de propiedad predeterminado, utilice el nombre de variable, con una lista de argumentos, a la izquierda de una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#14](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Siempre puede especificar el nombre de la propiedad predeterminada junto con el nombre de variable, tal como lo haría para tener acceso a cualquier otra propiedad.  
  
     [!code-vb[VbVbcnProcedures#19](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo se declara una propiedad predeterminada en una clase.  
  
 [!code-vb[VbVbcnProcedures#12](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se indica cómo se llama a la propiedad predeterminada `myProperty` en la clase `class1`.  Las tres instrucciones de asignación almacenan valores en `myProperty` y la llamada <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> lee los valores.  
  
 [!code-vb[VbVbcnProcedures#13](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 El uso más común de una propiedad predeterminada es la propiedad <xref:Microsoft.VisualBasic.Collection.Item%2A> en diversas clases de colección.  
  
## Programación eficaz  
 Las propiedades predeterminadas pueden producir una pequeña reducción en los caracteres del código fuente pero pueden dificultar la lectura del código.  Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de éstas, no puede estar seguro de si esta referencia tiene acceso a la clase o estructura en sí, o a una propiedad predeterminada.  Esto puede conducir a errores del compilador o a ligeros errores lógicos en tiempo de ejecución.  
  
 Puede reducir levemente las posibilidades de errores de propiedades predeterminadas utilizando siempre [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer la comprobación de tipos del compilador en `On`.  
  
 Si está pensando en utilizar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada, y si es así, cómo se llama.  
  
 Debido a estas desventajas, debería considerar no definir propiedades predeterminadas.  Para una mejor lectura del código, debería considerar asimismo hacer siempre una referencia explícita a todas las propiedades, incluso a las propiedades predeterminadas.  
  
## Vea también  
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)