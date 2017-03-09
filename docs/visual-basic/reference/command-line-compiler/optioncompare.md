---
title: "/optioncompare | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optioncompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optioncompare (opción del compilador) [Visual Basic]"
  - "optioncompare (opción del compilador) [Visual Basic]"
  - "-optioncompare (opción del compilador) [Visual Basic]"
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optioncompare
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica la forma de realizar las comparaciones de cadenas.  
  
## Sintaxis  
  
```  
/optioncompare:{binary | text}  
```  
  
## Comentarios  
 Puede especificar `/optioncompare` de dos formas: `/optioncompare:binary` para utilizar comparaciones de cadenas binarias y `/optioncompare:text` para utilizar comparaciones de cadena de texto.  De manera predeterminada, el compilador utiliza `/optioncompare:binary`.  
  
 En Microsoft Windows, la página de códigos que se utiliza determina el criterio de ordenación binario.  Un criterio de ordenación binario típico sería el siguiente:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 La comparación de cadenas basada en el texto utiliza un criterio de ordenación que no distingue entre mayúsculas y minúsculas y que se basa en la configuración de idioma del sistema.  Un criterio de ordenación de texto típico sería el siguiente:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### Para establecer \/optioncompare en el IDE de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Compilar**.  
  
3.  Modifique el valor en el cuadro **Option Compare**.  
  
### Para establecer \/optioncompare mediante programación  
  
-   Vea [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## Ejemplo  
 La siguiente línea compila P`rojFile.vb` y usa comparaciones binarias de cadenas.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)