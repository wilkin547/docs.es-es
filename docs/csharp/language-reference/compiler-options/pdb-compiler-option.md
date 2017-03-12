---
title: "/pdb (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/pdb"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-pdb compiler option [C#]"
  - "pdb compiler option [C#]"
  - "/pdb compiler option [C#]"
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# /pdb (C# Compiler Options)
La opción del compilador **\/pdb** especifica el nombre y ubicación del archivo de símbolos de depuración.  
  
## Sintaxis  
  
```  
/pdb:filename  
```  
  
## Argumentos  
 `filename`  
 Nombre y ubicación del archivo de símbolos de depuración.  
  
## Comentarios  
 Cuando especifica [\/debug \(Emit Debugging Information\)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), el compilador crea un archivo .pdb en el mismo directorio en el que creará el archivo de salida \(.exe o .dll\) con un nombre de archivo que es igual que el del archivo de salida.  
  
 **\/pdb** le permite especificar un nombre de archivo y ubicación no predeterminados para el archivo .pdb.  
  
 Esta opción del compilador no se puede establecer en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  
  
## Ejemplo  
 Compile `t.cs` y cree un archivo .pdb denominado tt.pdb:  
  
```  
csc /debug /pdb:tt t.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)