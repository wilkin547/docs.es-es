---
title: "/highentropyva (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/highentropyva"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/highentropyva compiler option [C#]"
  - "-highentropyva compiler option [C#]"
  - "highentropyva compiler option [C#]"
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# /highentropyva (C# Compiler Options)
La opción del compilador **\/highentropyva** indica el kernel de Windows si un ejecutable determinada admite el alto diseño Randomization \(ASLR\) del espacio de direcciones de la entropía.  
  
## Sintaxis  
  
```  
/highentropyva[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Esta opción especifica que un archivo ejecutable de 64 bits o un ejecutable que está marcada por la opción del compilador [\/platform: anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) admite un alto espacio de dirección virtual de la entropía.  La opción se deshabilita de forma predeterminada.  Uso **\/highentropyva\+** o **\/highentropyva** de hacerlo.  
  
## Comentarios  
 La opción de **\/highentropyva** permite a las versiones compatibles del kernel de Windows para utilizar grados superiores de entropía al aleatorizar el diseño del espacio de direcciones de un proceso como parte de ASLR.  Mediante grados superiores de entropía significa que un número mayor de direcciones puede ser asignado a las regiones de memoria como pilas y pilas.  Como resultado, es más difícil ver la ubicación de una región de memoria concreta.  
  
 Cuando se especifica la opción del compilador **\/highentropyva** , el destino ejecutable y cualquier módulo que depende deben ser capaces de controlar los valores de puntero que son mayores de 4 gigabytes de \(GB\) cuando se ejecuta como un proceso de 64 bits.  
  
 Para obtener más información sobre ASLR, vea [Mitigar vulnerabilidades de software](http://go.microsoft.com/fwlink/?LinkId=226234).