---
title: "#region (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#region"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#region (directiva) [C#]"
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #region (Referencia de C#)
`#region` permite especificar un bloque de código que se puede expandir o contraer cuando se utiliza la característica de [esquematización](/visual-studio/ide/outlining) del editor de código de Visual Studio.  En archivos de código de gran tamaño, resulta práctico si se puede contraer u ocultar una o varias regiones; esto permite enfocarse en la parte del archivo en la que se está trabajando.  En el siguiente ejemplo, se muestra cómo definir una región.  
  
```  
  
      #region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## Comentarios  
 Un bloque `#region` debe terminarse con una directiva [\#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).  
  
 Un bloque `#region` no se puede solapar con un bloque [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  Sin embargo, un bloque `#region` puede estar anidado en un bloque `#if` y un bloque `#if` puede estar anidado en un bloque `#region`.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)