---
title: "/noconfig (C# Compiler Options) | Microsoft Docs"
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
  - "/noconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/noconfig compiler option [C#]"
  - "csc.rsp"
  - "-noconfig compiler option [C#]"
  - "noconfig compiler option [C#]"
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /noconfig (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/noconfig** comunica al compilador que no compile con el archivo csc.rsp, que está ubicado y se carga desde el mismo directorio que el archivo csc.exe.  
  
## Sintaxis  
  
```  
/noconfig  
```  
  
## Comentarios  
 El archivo csc.rsp hace referencia a todos los ensamblados incluidos en .NET Framework.  Las referencias reales que incluye el entorno de desarrollo Visual Studio .NET dependen del tipo de proyecto.  
  
 Es posible modificar el archivo csc.rsp y especificar opciones de compiladores adicionales que puedan incluirse en cada compilación desde la línea de comandos con csc.exe \(excepto la opción **\/noconfig**\).  
  
 El compilador procesa en último lugar las opciones que se pasan al comando **csc**.  Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo csc.rsp.  
  
 Si no desea que el compilador busque y utilice la configuración del archivo csc.rsp, especifique **\/noconfig**.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)