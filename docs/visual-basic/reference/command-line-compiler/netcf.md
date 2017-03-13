---
title: "/netcf | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/netcf"
  - "netcf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/netcf (opción del compilador) [Visual Basic]"
  - "netcf (opción del compilador) [Visual Basic]"
  - "-netcf (opción del compilador) [Visual Basic]"
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /netcf
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Establece el compilador con destino [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  
  
## Sintaxis  
  
```  
/netcf  
```  
  
## Comentarios  
 La opción `/netcf` hace que el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] tenga como destino [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] en lugar de la versión completa de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  La funcionalidad del lenguaje que únicamente está presente en la versión completa de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] se deshabilita.  
  
 La opción `/netcf` se ha diseñado para utilizarse con [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).  Las características del lenguaje deshabilitadas por `/netcf` son las mismas que no están presentes en los archivos de destino de `/sdkpath`.  
  
> [!NOTE]
>  La opción `/netcf` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  La opción `/netcf` se establece cuando se carga un proyecto de dispositivo de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 La opción `/netcf` cambia las características de lenguaje siguientes:  
  
-   La palabra clave [End \<palabra clave\> \(Instrucción\)](../../../visual-basic/language-reference/statements/end-keyword-statement.md), que finaliza la ejecución de un programa, está deshabilitada.  El programa siguiente lleva a cabo la compilación y la ejecución son `/netcf` pero produce un error en tiempo de compilación con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   El enlace en tiempo de ejecución, en todas sus formas, se deshabilita.  Cuando se encuentran escenarios de enlace en tiempo de ejecución, se generan errores en tiempo de compilación.  El programa siguiente lleva a cabo la compilación y la ejecución son `/netcf` pero produce un error en tiempo de compilación con `/netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   Los modificadores [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) y[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) están deshabilitados.  La sintaxis de la instrucción [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md) también cambia a `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.  En el ejemplo de código siguiente se muestra el efecto de `/netcf` en una compilación:  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Si se utilizan las palabras clave de Visual Basic 6.0 que se quitaron de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], se produce un error diferente que cuando se utiliza `/netcf`.  Esto afecta a los mensajes de error que se muestran para las siguientes palabras clave:  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## Ejemplo  
 En el código siguiente se compila `Myfile.vb` con [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)], usando las versiones de Mscorlib.dll y Microsoft.VisualBasic.dll que se encuentran en el directorio de instalación predeterminado de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] en la unidad C.  Normalmente, se usa la versión más reciente de [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)].  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)