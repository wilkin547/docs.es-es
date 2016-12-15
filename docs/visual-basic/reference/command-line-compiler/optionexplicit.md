---
title: "/optionexplicit | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/optionexplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionexplicit (opción del compilador) [Visual Basic]"
  - "optionexplicit (opción del compilador) [Visual Basic]"
  - "-optionexplicit (opción del compilador) [Visual Basic]"
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optionexplicit
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador notifique errores si no se declaran las variables antes de utilizarlas.  
  
## Sintaxis  
  
```  
/optionexplicit[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  Especifique `/optionexplicit+` para requerir la declaración explícita de variables.  La opción `/optionexplicit+` es el valor predeterminado y es igual que `/optionexplicit`.  La opción `/optionexplicit-` habilita la declaración implícita de variables.  
  
## Comentarios  
 Si el archivo de código fuente contiene [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción invalida la configuración del compilador de línea de comandos `/optionexplicit`.  
  
### Para establecer \/optionexplicit en el IDE de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Compilar**.  
  
3.  Modifique el valor en el cuadro **Option Explicit**.  
  
## Ejemplo  
 Las siguientes líneas de código compilan cuando se utiliza `/optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Explicit \(Instrucción\)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)