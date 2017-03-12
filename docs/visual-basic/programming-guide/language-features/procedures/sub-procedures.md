---
title: "Subprocedimientos (Visual Basic) | Microsoft Docs"
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
  - "procedimientos, llamar"
  - "procedimientos, Sub"
  - "bloques de instrucciones"
  - "Sub (procedimientos)"
  - "Sub (procedimientos), acerca de los procedimientos Sub"
  - "Sub (procedimientos), llamar"
  - "Sub (procedimientos), sintaxis"
  - "sintaxis, Sub (procedimientos)"
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Subprocedimientos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento `Sub` es una serie de instrucciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] delimitadas por las instrucciones `Sub` y `End Sub`.  El procedimiento `Sub` ejecuta una tarea y devuelve el control al código de llamada, pero no le devuelve un valor.  
  
 Cada vez que se llama a un procedimiento, se ejecutan las instrucciones de éste, desde la primera instrucción ejecutable tras la instrucción `Sub` hasta la primera instrucción `End Sub`, `Exit Sub` o `Return` que se encuentre.  
  
 Se puede definir un procedimiento `Sub` en módulos, clases y estructuras.  Es `Public` de forma predeterminada, lo que significa que puede llamarlo desde cualquier lugar de la aplicación que tenga acceso al módulo, clase o estructura en el que se ha definido.  El término *método* describe un procedimiento `Sub` o `Function` al que se tiene acceso desde fuera de su módulo, clase o estructura en el que se ha definido.  Para obtener más información, vea [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md).  
  
 Un procedimiento `Sub` puede aceptar argumentos, como constantes, variables o expresiones, que le pasa el código de llamada.  
  
## Sintaxis de la declaración  
 La sintaxis para declarar un procedimiento `Sub` es la siguiente:  
  
 `[` *modificadores* `] Sub`  *subNombre* `[(` *listaDeParámetros* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Los objetos `modifiers` pueden especificar un nivel de acceso e información acerca de la sobrecarga, invalidación, uso compartido y sombreado.  Para obtener más información, vea [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Declaración de parámetros  
 Puede declarar un parámetro del procedimiento de igual forma que lo haría con una variable, especificando el nombre de parámetro y el tipo de datos.  También puede especificar el mecanismo para pasar argumentos y si el parámetro es opcional o una matriz de parámetros.  
  
 La sintaxis de los parámetros de una lista de parámetros es la siguiente:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *nombreDeParámetro*  `As`  *tipoDeDatos*  
  
 Si el parámetro es opcional, debe proporcionar también un valor predeterminado como parte de su declaración.  La sintaxis para especificar un valor predeterminado es la siguiente:  
  
 `Optional [ByVal | ByRef]`  *nombreDeParámetro*  `As`  *tipoDeDatos*  `=`  *valorPredeterminado*  
  
### Parámetros como variables locales  
 Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local.  Esto significa que su de duración es igual a la del procedimiento y su ámbito es el procedimiento completo.  
  
## Sintaxis de llamada  
 Los procedimientos `Sub` se invocan de forma explícita, con una instrucción de llamada independiente.  No se les puede llamar utilizando su nombre en una expresión.  Debe suministrar valores para todos los argumentos que no sean opcionales e incluir la lista de argumentos entre paréntesis.  Si no se proporcionan argumentos, se puede omitir el paréntesis.  El uso de la palabra clave `Call` es opcional aunque no recomendado.  
  
 La sintaxis para llamar a un procedimiento `Sub` es la siguiente:  
  
 `[Call]`  *subNombre* `[(` *listaDeArgumentos* `)]`  
  
 Puede llamar a un método `Sub` desde fuera de la clase que lo define.  Primero, tiene que utilizar la palabra clave `New` para crear una instancia de la clase o llamar a un método que devuelva una instancia de la clase.  Para obtener más información, vea [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md).  A continuación, puede utilizar la sintaxis siguiente para llamar al método `Sub` en el objeto de instancia:  
  
 *Object*.*methodname*`[(`*argumentlist*`)]`  
  
### Ejemplo de declaración y llamada  
 El procedimiento `Sub` que aparece a continuación notifica al usuario del equipo la tarea que está a punto de realizar la aplicación, y también muestra una marca de tiempo.  En lugar de duplicar este código al principio de cada tarea, la aplicación simplemente llama a  `tellOperator`  desde varios lugares.  Cada llamada pasa una cadena al argumento  `task`  que identifica la tarea que se va a iniciar.  
  
 [!code-vb[VbVbcnProcedures#2](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/sub-procedures_1.vb)]  
  
 El ejemplo siguiente muestra una llamada típica a  `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/sub-procedures_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Cómo: Llamar a un procedimiento que no devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [Cómo: Llamar a un controlador de eventos en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)