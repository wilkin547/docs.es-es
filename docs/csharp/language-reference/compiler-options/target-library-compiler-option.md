---
title: "/target:library (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:library"
  - "target compiler options [C#], /target:library"
  - "/target compiler options [C#], /target:library"
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# /target:library (C# Compiler Options)
La opción **\/target:library** hace que el compilador cree una biblioteca de vínculos dinámicos \(DLL\) en lugar de un archivo ejecutable \(EXE\).  
  
## Sintaxis  
  
```  
/target:library  
```  
  
## Comentarios  
 Se creará el archivo DLL con la extensión .dll.  
  
 A menos que se especifique lo contrario con la opción [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del primer archivo de entrada.  
  
 Cuando se especifica en la línea de comandos, se utilizan todos los archivos hasta la siguiente opción **\/out** o **\/target:module** para crear el archivo .dll.  
  
 Para compilar un archivo .dll, no es necesario un método [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de resultado**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Ejemplo  
 Compile `in.cs`, creando `in.dll`:  
  
```  
csc /target:library in.cs  
```  
  
## Vea también  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)