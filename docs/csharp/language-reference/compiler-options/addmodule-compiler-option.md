---
title: "/addmodule (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/addmodule"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/addmodule compiler option [C#]"
  - "-addmodule compiler option [C#]"
  - "addmodule compiler option [C#]"
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /addmodule (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Esta opción agrega un módulo creado con el modificador target:module para la compilación actual.  
  
## Sintaxis  
  
```  
/addmodule:file[;file2]  
```  
  
## Argumentos  
 `file`, `file2`  
 Archivo de salida que contiene metadatos.  Este archivo no puede contener un manifiesto del ensamblado.  Para importar más de un archivo, hay que separar los nombres de archivo con comas o puntos y comas.  
  
## Comentarios  
 Todos los módulos agregados mediante **\/addmodule** deben hallarse en el mismo directorio que el archivo de salida en tiempo de ejecución.  Es decir, se puede especificar un módulo de cualquier directorio en el momento de la compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución.  Si dicho módulo no se encuentra en el directorio de la aplicación en tiempo de ejecución, se obtiene la excepción <xref:System.TypeLoadException>.  
  
 `file` no puede contener un ensamblado.  Por ejemplo, si el archivo de salida se creó con [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), se pueden importar sus metadatos con **\/addmodule**.  
  
 Si se creó el archivo de salida con una opción **\/target** diferente de **\/target:module**, no se podrán importar sus metadatos con **\/addmodule**, pero sí con [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Esta opción del compilador no está disponible en Visual Studio; en un proyecto no se puede hacer referencia a un módulo.  Además, esta opción del compilador no se puede modificar mediante programación.  
  
## Ejemplo  
 Para compilar el archivo de código fuente `input.cs` y agregar metadatos de `metad1.netmodule` y `metad2.netmodule` para generar `out.exe`, ejecute:  
  
```  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Ensamblados de varios archivos](../Topic/Multifile%20Assemblies.md)   
 [Cómo: Compilar un ensamblado de varios archivos](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)