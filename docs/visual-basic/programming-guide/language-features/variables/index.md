---
title: "Variables en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "valores [Visual Basic], almacenar"
  - "variables [Visual Basic]"
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Variables en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Al realizar cálculos con [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], resulta frecuente tener que almacenar valores.  Por ejemplo, puede que necesite calcular varios valores, compararlos y realizar distintas operaciones con ellos, en función del resultado de la comparación.  Si desea comparar los valores, tiene que conservarlos.  
  
## Uso  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], al igual que la mayoría de los lenguajes de programación, usa variables para almacenar los valores.  Una *variable* tiene un nombre \(la palabra que se usa para referirse al valor que contiene la variable\).  Una variable también tiene un tipo de datos, que determina el tipo de datos que puede almacenar la variable.  Una variable puede representar una matriz si tiene que almacenar un conjunto indizado de elementos de datos estrechamente relacionados entre sí.  
  
 La inferencia de tipos de variable local permite declarar las variables sin tener que indicar de forma explícita un tipo de datos.  En lugar de ello, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.  Para obtener más información, vea [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) y [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Asignar valores  
 Para efectuar cálculos y asignar el resultado a una variable, se utilizan instrucciones de asignación, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  El signo igual \(`=`\) de este ejemplo es un operador de asignación, no un operador de igualdad.  El valor se asigna a la variable `applesSold`.  
  
 Para obtener más información, vea [Cómo: Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## Variables y propiedades  
 Es  si el elemento pertenece a esta vista de colección; de lo contrario, es .  Sin embargo, es más complejo que una variable.  Una propiedad utiliza bloques de código que controlan cómo establecer y recuperar su valor.  Para obtener más información, vea [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## Vea también  
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Solucionar problemas de variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)   
 [Cómo: Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)