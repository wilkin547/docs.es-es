---
title: "/target:module (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:module"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:module"
  - "target compiler options [C#], /target:module"
  - "/target compiler options [C#], /target:module"
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:module (C# Compiler Options)
Esta opción hace que el compilador no genere un manifiesto del ensamblado.  
  
## Sintaxis  
  
```  
/target:module  
```  
  
## Comentarios  
 De forma predeterminada, el archivo de salida creado compilando con esta opción tendrá una extensión .netmodule.  
  
 Common Language Runtime de .NET Framework no puede cargar un archivo sin manifiesto del ensamblado.  No obstante, puede incorporar ese archivo al manifiesto del ensamblado mediante [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Si se crea más de un módulo en una sola compilación, los tipos [internal](../../../csharp/language-reference/keywords/internal.md) de un módulo estarán disponibles para el resto de módulos de la compilación.  Cuando el código de un módulo hace referencia a los tipos `internal` de otro módulo, ambos módulos deben incorporarse a un manifiesto del ensamblado mediante **\/addmodule**.  
  
 El entorno de desarrollo de Visual Studio no permite la creación de módulos.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Ejemplo  
 Compile `in.cs`, creando `in.netmodule`:  
  
```  
csc /target:module in.cs  
```  
  
## Vea también  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)