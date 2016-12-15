---
title: "/nowarn (C# Compiler Options) | Microsoft Docs"
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
  - "/nowarn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowarn compiler option [C#]"
  - "/nowarn compiler option [C#]"
  - "-nowarn compiler option [C#]"
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /nowarn (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/nowarn** permite evitar que el compilador muestre una o más advertencias.  Si hay varios números de advertencia, hay que separarlos con una coma.  
  
## Sintaxis  
  
```  
/nowarn:number1[,number2,...]  
```  
  
## Argumentos  
 `number1`, `number2`  
 Número o números de advertencia que el compilador debe suprimir.  
  
## Comentarios  
 Sólo se debe especificar la parte numérica del identificador de advertencia.  Por ejemplo, si se desea suprimir CS0028, hay que especificar `/nowarn:28`.  
  
 El compilador omitirá silenciosamente los números de advertencias que se han pasado a `/nowarn`, que eran válidas en versiones anteriores, pero que se han quitado del compilador.  Por ejemplo, CS0679 era válida para el compilador en Visual Studio .NET 2002, pero posteriormente se ha quitado.  
  
 La opción `/nowarn` no puede suprimir las advertencias siguientes:  
  
-   Advertencia del compilador \(nivel 1\) CS2002  
  
-   Advertencia del compilador \(nivel 1\) CS2023  
  
-   Advertencia del compilador \(nivel 1\) CS2029  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  Para obtener información detallada, vea [Compilar \(Página, Diseñador de proyectos\) \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Modifique el valor de la propiedad **Suprimir advertencias**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)