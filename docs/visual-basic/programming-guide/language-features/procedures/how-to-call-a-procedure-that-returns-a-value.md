---
title: "C&#243;mo: Llamar a un procedimiento que devuelve un valor (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "llamadas a procedimientos, devolver valores"
  - "procedimientos, llamar"
  - "procedimientos, devolver un valor"
  - "código de Visual Basic, procedimientos"
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Llamar a un procedimiento que devuelve un valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento `Function` devuelve un valor al código de llamada.  Para llamar a un procedimiento, hay que incluir el nombre y los argumentos de éste en la parte derecha de una instrucción de asignación o en una expresión.  
  
### Para llamar a un procedimiento Function dentro de una expresión  
  
1.  Utilice el nombre del procedimiento `Function` del mismo modo que utilizaría una variable.  Puede utilizar una llamada al procedimiento `Function` en cualquier parte de la expresión en la que utilizaría una variable o una constante.  
  
2.  Agregue paréntesis después del nombre del procedimiento para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  Sin embargo, los paréntesis hacen que el código sea más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que el procedimiento `Function` define los parámetros correspondientes.  
  
     Si lo desea, puede transferir también uno o varios argumentos por nombre.  Para obtener más información, vea [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
4.  El valor devuelto desde el procedimiento participa en la expresión del mismo modo que lo haría una variable o una constante.  
  
### Para llamar a un procedimiento Function en una instrucción de asignación  
  
1.  Utilice el nombre del procedimiento `Function` situado detrás del signo igual \(`=`\) en una instrucción de asignación.  
  
2.  Agregue paréntesis después del nombre del procedimiento para incluir entre ellos la lista de argumentos.  Si no hay ningún argumento, puede omitir opcionalmente los paréntesis.  Sin embargo, los paréntesis hacen que el código sea más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis y separados por comas.  Asegúrese de proporcionar los argumentos en el mismo orden en que el procedimiento `Function` define los parámetros correspondientes, a menos que los esté transfiriendo por nombre.  
  
4.  El valor devuelto desde el procedimiento se almacena en la variable o propiedad situada en el lado izquierdo de la instrucción de asignación.  
  
## Ejemplo  
 En el ejemplo siguiente se llama a la función <xref:Microsoft.VisualBasic.Interaction.Environ%2A> de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para recuperar el valor de una variable de entorno del sistema operativo.  La primera línea llama a la función `Environ` en una expresión y la segunda línea la invoca en una instrucción de asignación.  `Environ` toma el nombre de variable como único argumento.  Devuelve el valor de la variable al código de llamada.  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## Vea también  
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Cómo: Crear un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Cómo: Devolver un valor de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Cómo: Llamar a un procedimiento que no devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)