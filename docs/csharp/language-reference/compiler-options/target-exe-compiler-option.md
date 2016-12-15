---
title: "/target:exe (C# Compiler Options) | Microsoft Docs"
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
  - "/exe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#], /target:exe"
  - "/target compiler options [C#], /target:exe"
  - "-target compiler options [C#], /target:exe"
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:exe (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/target:exe** hace que el compilador cree una aplicación de consola ejecutable \(EXE\).  
  
## Sintaxis  
  
```  
/target:exe  
```  
  
## Comentarios  
 La opción **\/target:exe**está activada de manera predeterminada.  El archivo ejecutable se creará con la extensión .exe.  
  
 Se utiliza [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) para crear un programa ejecutable de Windows.  
  
 A menos que se especifique otra cosa con la opción [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md).  
  
 Cuando se especifica en la línea de comandos, se utilizan todos los archivos hasta la siguiente opción **\/out** o **\/target:module** para crear el archivo .exe.  
  
 Sólo se requiere un método **Main** en los archivos de código fuente que se compilan para producir un .exe.  La opción [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) del compilador permite especificar la clase que contiene el método **Main**, en casos en los que el código tiene más de una clase con un método **Main**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Tipo de resultado**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Ejemplo  
 Cada una de las siguientes líneas de comandos compilará `in.cs` y creará `in.exe`:  
  
```  
csc /target:exe in.cs  
csc in.cs  
```  
  
## Vea también  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)