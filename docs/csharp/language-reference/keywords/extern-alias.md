---
title: "alias externo (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "alias_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "alias [C#], extern (palabra clave)"
  - "alias, extern (palabra clave)"
  - "alias externo (palabra clave) [C#]"
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# alias externo (Referencia de C#)
Puede que tenga que hacer referencia a dos versiones de ensamblados que tengan los mismos nombres completos de tipo.  Por ejemplo, es posible que tenga que utilizar dos o más versiones de un ensamblado en la misma aplicación.  Al utilizar un alias de ensamblado externo, los espacios de nombres de cada ensamblado se pueden ajustar dentro de espacios de nombres de nivel de raíz denominados por el alias, lo que permite utilizarlos en el mismo archivo.  
  
> [!NOTE]
>  La palabra clave [extern](../../../csharp/language-reference/keywords/extern.md) también se utiliza como un modificador de método, cuando se declara un método escrito en código no administrado.  
  
 Para hacer referencia a dos ensamblados con los mismos nombres completos de tipo, debe especificarse un alias en el símbolo del sistema, del modo siguiente:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Esto crea los alias externos `GridV1` y `GridV2`.  Para utilizar estos alias desde dentro de un programa, haga referencia a ellos mediante la palabra clave `extern`.  Por ejemplo:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que crea un paralelo \(pero no se encuentra dentro de él\) al espacio de nombres global.  De este modo, es posible hacer referencia a los tipos de cada ensamblado sin ambigüedades, mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.  
  
 En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll` y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [:: \(operador\)](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)