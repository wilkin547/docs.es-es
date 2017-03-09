---
title: "/optioninfer | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioninfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optioninfer (opción del compilador) [Visual Basic]"
  - "optioninfer (opción del compilador) [Visual Basic]"
  - "-optioninfer (opción del compilador) [Visual Basic]"
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /optioninfer
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.  
  
## Sintaxis  
  
```  
/optioninfer[+ | -]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`+`  &#124; `-`|Opcional.  Especifique `/optioninfer+` para habilitar la inferencia de tipo de variable local o `/optioninfer-` para bloquearla.  La opción `/optioninfer`, sin ningún valor especificado, es igual a `/optioninfer+`.  El valor predeterminado cuando el modificador `/optioninfer` no está presente también es `/optioninfer+`.  El valor predeterminado se establece en el archivo de respuesta vbc.rsp.|  
  
> [!NOTE]
>  Puede utilizar la opción `/noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp.  El valor predeterminado del compilador para esta opción es `/optioninfer-`.  
  
## Comentarios  
 Si el archivo de código fuente contiene una [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md), la declaración reemplaza la configuración `/optioninfer` del compilador de la línea de comandos.  
  
### Cómo establecer \/optioninfer en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/es-es/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  En la ficha **Compilar**, modifique el valor del cuadro **Option infer**.  
  
## Ejemplo  
 El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)