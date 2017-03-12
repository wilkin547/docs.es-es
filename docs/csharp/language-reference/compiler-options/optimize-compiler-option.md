---
title: "/optimize (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/optimize"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/optimize compiler option [C#]"
  - "-o compiler option [C#]"
  - "optimize compiler option [C#]"
  - "/o compiler option [C#]"
  - "-optimize compiler option [C#]"
  - "compiler optimization [C#]"
  - "o compiler option [C#]"
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /optimize (C# Compiler Options)
La opción **\/optimize**habilita o deshabilita las optimizaciones realizadas por el compilador para hacer que el archivo de salida sea más pequeño, rápido y eficiente.  
  
## Sintaxis  
  
```  
/optimize[+ | -]  
```  
  
## Comentarios  
 **\/optimize** también indica a Common Language Runtime que optimice el código en tiempo de ejecución.  
  
 De forma predeterminada, las optimizaciones están deshabilitadas.  Especifique **\/optimize\+** para habilitar las optimizaciones.  
  
 Cuando compile un módulo para que lo utilice un ensamblado, utilice la misma configuración **\/optimize** que para el propio ensamblado.  
  
 **\/o** es la forma abreviada de **\/optimize**.  
  
 Se pueden combinar las opciones **\/optimize** y [\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Modifique la propiedad **Optimizar código**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## Ejemplo  
 Para compilar `t2.cs`  y habilitar las optimizaciones del compilador, ejecute:  
  
```  
csc t2.cs /optimize  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)