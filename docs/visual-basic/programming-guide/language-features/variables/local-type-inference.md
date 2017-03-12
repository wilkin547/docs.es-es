---
title: "Inferencia de tipo de variable local (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "local type inference"
  - "vb.TypeInfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables locales con asignación implícita de tipos [Visual Basic]"
  - "inferencia [Visual Basic]"
  - "inferencia de tipos de variable local [Visual Basic]"
  - "Option Infer (instrucción)"
  - "inferencia de tipos [Visual Basic]"
  - "variables [Visual Basic], inferencia de tipos"
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 43
---
# Inferencia de tipo de variable local (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador de Visual Basic utiliza la *inferencia de tipos* para determinar los tipos de datos de las variables locales declarados sin ninguna cláusula `As`.  El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.  Esto le permite declarar variables sin indicar explícitamente un tipo, como se muestra en el siguiente ejemplo. Como resultado de las declaraciones, `num1` y `num2` están fuertemente tipadas como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_1.vb)]  
  
> [!NOTE]
>  Si no desea que `num2` del ejemplo anterior vaya a tener un tipo como `Integer`, puede especificar otro tipo mediante una declaración como `Dim num3 As Object = 3` o `Dim num4 As Double = 3`.  
  
 La inferencia de tipo de variable local se aplica en el nivel de procedimiento.  No se puede utilizar para declarar variables en el nivel de módulo \(en una clase, una estructura, un módulo o una interfaz pero no en un procedimiento o en un bloque\).  Si `num2`, en el ejemplo anterior, fuese un campo de una clase en vez de una variable local en un procedimiento, la declaración provocaría un error con la instrucción `Option Strict` activada y clasificaría `num2` como `Object` con la instrucción `Option Strict` desactivada.  Del mismo modo, la inferencia de tipos de variable local no se aplica a las variables de nivel de procedimiento declaradas como `Static`.  
  
## Inferencia de tipos yenlace en tiempo de ejecución  
 El código que usa la inferencia de tipos se parece al código que depende del enlace en tiempo de ejecución.  Sin embargo, la inferencia de tipos permite el establecimiento inflexible de los tipos de la variable en lugar de dejarla como `Object`.  El compilador utiliza el inicializador de una variable para determinar su tipo en tiempo de compilación con el fin de generar código de enlace en tiempo de compilación.  En el ejemplo anterior, `num2`, al igual que `num1`, queda tipado como `Integer`.  
  
 El comportamiento de las variables de enlace en tiempo de compilación difiere del de las variables de enlace en tiempo de ejecución, cuyo tipo sólo se conoce en tiempo de ejecución.  Si se sabe el tipo pronto, el compilador puede identificar los problemas antes de la ejecución, asignar la memoria con precisión y realizar otras optimizaciones.  El enlace en tiempo de compilación también permite que el entorno de desarrollo integrado \(IDE\) de Visual Basic proporcione ayuda de IntelliSense sobre los miembros de un objeto.  El enlace en tiempo de compilación también se prefiere por razones de rendimiento.  Esto ocurre porque todos los datos almacenados en una variable de enlace en tiempo de ejecución se deben ajustar como tipo `Object` y si se tiene acceso a los miembros del tipo en tiempo de ejecución, el programa se ejecuta más lentamente.  
  
## Ejemplos  
 La inferencia de tipos se produce cuando una variable local se declara sin una cláusula `As` y se inicializa.  El compilador utiliza el tipo del valor inicial asignado como tipo de la variable.  Por ejemplo, cada una de las líneas de código siguientes declara una variable de tipo `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_2.vb)]  
  
 El código siguiente muestra dos maneras equivalentes de crear una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_3.vb)]  
  
 Conviene utilizar la inferencia de tipos para determinar el tipo de una variable de control de bucle.  En el código siguiente, el compilador deduce que `number` es `Integer` porque `someNumbers2`, según el ejemplo anterior, es una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_4.vb)]  
  
 La inferencia de tipo de variable local se puede utilizar en instrucciones `Using` para establecer el tipo del nombre del recurso, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_5.vb)]  
  
 El tipo de una variable también se puede deducir de los valores devueltos de las funciones, como muestra el ejemplo siguiente.  Tanto `pList1` como `pList2` son matrices de procesos porque `Process.GetProcesses` devuelve una matriz de procesos.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/local-type-inference_6.vb)]  
  
## Option Infer  
 permisos de`Option Infer` que especifica si la inferencia de tipo de variable local se permite en un archivo determinado.  Para habilitar o bloquear la opción, escriba una de las instrucciones siguientes al principio del archivo.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Si no especifica un valor para `Option Infer` en el código, el valor predeterminado del compilador es `Option Infer On`.  Para los proyectos actualizados de [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb-orcas-long-md.md)] o versiones anteriores, el valor predeterminado del compilador es `Option Infer Off`.  
  
 Si el valor que se establece para `Option Infer` en un archivo está en conflicto con el valor establecido en el IDE o la línea de comandos, tiene prioridad el valor del archivo.  
  
 Para obtener más información, vea [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  
  
## Restricciones  
 La inferencia de tipo sólo se puede utilizar para las variables locales no estáticas; no se puede usar para determinar el tipo de los campos de clase, las propiedades o las funciones.  
  
## Vea también  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [\/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)