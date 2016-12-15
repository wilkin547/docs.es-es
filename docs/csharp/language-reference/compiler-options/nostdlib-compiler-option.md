---
title: "/nostdlib (C# Compiler Options) | Microsoft Docs"
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
  - "/nostdlib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nostdlib compiler option [C#]"
  - "-nostdlib compiler option [C#]"
  - "/nostdlib compiler option [C#]"
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /nostdlib (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.  
  
## Sintaxis  
  
```  
/nostdlib[+ | -]  
```  
  
## Comentarios  
 Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.  
  
 Si no se especifica **\/nostdlib**, el archivo mscorlib.dll se importará en el programa \(equivale a especificar **\/nostdlib\-**\). Especificar **\/nostdlib** es lo mismo que especificar **\/nostdlib\+**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **No hacer referencia al archivo mscorlib.dll**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)