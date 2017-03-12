---
title: "/target:winexe (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:winexe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/target compiler options [C#], /target:winexe"
  - "-target compiler options [C#], /target:winexe"
  - "target compiler options [C#], /target:winexe"
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:winexe (C# Compiler Options)
La opción **\/target:winexe** hace que el compilador cree un programa de Windows ejecutable \(EXE\).  
  
## Sintaxis  
  
```  
/target:winexe  
```  
  
## Comentarios  
 El archivo ejecutable se creará con la extensión .exe.  Los programas para Windows proporcionan una interfaz de usuario para la biblioteca de .NET Framework o con las API Win32.  
  
 Se utiliza [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) para crear una aplicación de consola.  
  
 A menos que se especifique otra cosa con la opción [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
 Cuando se especifica en la línea de comandos, todos los archivos hasta la siguiente opción **\/out** o [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) se utilizan para crear el programa de Windows.  
  
 Sólo se requiere un método **Main** en los archivos de código fuente que se compilan para producir un .exe.  La opción [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) permite especificar la clase que contiene el método **Main**, en casos en los que el código tiene más de una clase con un método **Main**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de resultado**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Ejemplo  
 Para compilar `in.cs` en un programa de Windows, ejecute:  
  
```  
csc /target:winexe in.cs  
```  
  
## Vea también  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)