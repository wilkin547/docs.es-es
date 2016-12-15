---
title: "#pragma warning (Referencia de C#) | Microsoft Docs"
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
  - "#pragma warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma (advertencia) (C#)"
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #pragma warning (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#pragma warning` puede habilitar o deshabilitar ciertas advertencias.  
  
## Sintaxis  
  
```  
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### Parámetros  
 `warning-list`  
 Es una lista de números de advertencia separados por coma.  Escriba los números solos, sin el prefijo "CS".  
  
 Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` las habilita todas.  
  
> [!NOTE]
>  Para encontrar números de advertencia en Visual Studio, compile el proyecto y, a continuación, busque dichos números en la ventana de salida .  
  
## Ejemplo  
  
```  
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, 3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore 3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)