---
title: "Option Explicit (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Explicit"
  - "vb.OptionExplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarar variables, explicit"
  - "Explicit (palabra clave)"
  - "declaración explícita de variables"
  - "declaración forzada de variables en la instrucción Option Explicit"
  - "Option Explicit (instrucción)"
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Option Explicit (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Fuerza la declaración explícita de todas las variables de un archivo, o permite declaraciones implícitas de variables.  
  
## Sintaxis  
  
```  
Option Explicit { On | Off }  
```  
  
## Elementos  
 `On`  
 Opcional.  Habilita la comprobación `Option Explicit`.  Si no se especifica `On` u `Off`, el valor predeterminado es `On`.  
  
 `Off`  
 Opcional.  Deshabilita la comprobación `Option Explicit`.  
  
## Comentarios  
 Cuando `Option Explicit On` o `Option Explicit` aparece en un archivo, se deben declarar explícitamente todas las variables mediante las instrucciones `Dim` o `ReDim`.  Si intenta usar un nombre de variable no declarada, se producirá un error en tiempo de compilación.  La instrucción `Option Explicit Off` permite la declaración implícita de variables.  
  
 Si se utiliza, la instrucción `Option Explicit` tiene que aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
> [!NOTE]
>  Establecer `Option Explicit` en `Off` generalmente no es una buena práctica.  Pudo escribir un nombre de variable incorrectamente en una o más ubicaciones, lo que podría causar resultados inesperados cuando se ejecute el programa.  
  
## Cuando no existe una instrucción Option Explicit  
 Si el código fuente no contiene una instrucción `Option Explicit`, se utiliza el valor de **Option Explicit** en [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) .  Si se utiliza el compilador de línea de comandos, se utiliza la opción del compilador [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md).  
  
#### Para establecer Option Explicit en el IDE  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Compilar**.  
  
3.  Establezca el valor en el cuadro **Option Explicit**.  
  
 Cuando se crea un nuevo proyecto, el valor de **Option Explicit** en la pestaña **Compilación** se establece en el valor de **Option Explicit** en el cuadro de diálogo **Valores predeterminados de VB**.  Para obtener acceso al cuadro de diálogo **Valores predeterminados de VB**, en el menú **Herramientas**, haga clic en **Opciones**.  En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, a continuación, haga clic en **Valores predeterminados de VB**.  El valor predeterminado inicial de **Valores predeterminados de VB** es `On`.  
  
#### Para establecer Option Explicit en la línea de comandos  
  
-   Incluya la opción del compilador [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) en el comando **vbc**.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Option Explicit` para exigir la declaración explícita de todas las variables.  Si intenta utilizar una variable no declarada, se producirá un error en tiempo de compilación.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-explicit-statement_2.vb)]  
  
## Vea también  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim \(Instrucción\)](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)