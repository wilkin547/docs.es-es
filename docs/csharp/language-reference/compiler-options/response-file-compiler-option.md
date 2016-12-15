---
title: "@ (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "@"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "response files, specifying for compilation [C#]"
  - "@ compiler option"
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# @ (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción @ permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.  
  
## Sintaxis  
  
```  
@response_file  
```  
  
## Argumentos  
 `response_file`  
 Archivo que especifica opciones del compilador o archivos de código fuente para compilar.  
  
## Comentarios  
 El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubiesen especificado en la línea de comandos.  
  
 Para especificar varios archivos de respuesta en una compilación, hay que especificar varias opciones de archivo de respuesta.  Por ejemplo:  
  
```  
@file1.rsp @file2.rsp  
```  
  
 En una misma línea de un archivo de respuesta, pueden aparecer varias opciones del compilador y archivos de código fuente.  Una especificación de opción del compilador debe aparecer en una única línea \(no puede abarcar varias líneas\).  Los archivos de respuesta pueden contener comentarios que empiezan con el símbolo \#.  
  
 Especificar opciones del compilador desde un archivo de respuesta produce el mismo efecto que incluir esas opciones en la línea de comandos.  Para obtener más información, vea [Compilar desde la línea de comandos](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 El compilador procesa las opciones de comandos según las encuentra.  Por consiguiente, los argumentos de la línea de comandos pueden reemplazar opciones enumeradas anteriormente en archivos de respuesta.  A la inversa, las opciones de un archivo de respuesta reemplazarán opciones incluidas previamente en la línea de comandos o en otros archivos de respuesta.  
  
 C\# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe.  Para obtener más información acerca de csc.rsp, vea [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).  
  
 Esta opción del compilador no se puede establecer en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## Ejemplo  
 A continuación, se muestran algunas líneas de un archivo de respuesta de ejemplo:  
  
```  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)