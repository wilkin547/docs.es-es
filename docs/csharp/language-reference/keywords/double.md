---
title: "double (Referencia de C#) | Microsoft Docs"
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
  - "double"
  - "double_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "double (tipo de datos) [C#]"
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# double (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `double` denota un tipo simple que almacena valores de punto flotante de 64 bits.  La siguiente tabla muestra la precisión y el intervalo de valores aproximado para el tipo `double`.  
  
|Tipo|Intervalo aproximado|Precisión|Tipo de .NET Framework|  
|----------|--------------------------|---------------|----------------------------|  
|`double`|±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup>|15\-16 dígitos|<xref:System.Double?displayProperty=fullName>|  
  
## Literales  
 De forma predeterminada, un literal numérico real en el lado derecho del operador de asignación se trata como un valor de tipo `double`.  No obstante, si desea tratar un número entero como `double`, utilice el sufijo d o D, por ejemplo:  
  
```  
  
double x = 3D;  
```  
  
## Conversiones  
 Es posible combinar tipos enteros numéricos y tipos de punto flotante en una expresión.  En este caso, los tipos enteros se convierten en tipos de punto flotante.  La evaluación de la expresión se realiza según las siguientes reglas:  
  
-   Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de las expresiones relacionales o booleanas.  
  
-   Si no existe ningún tipo `double` en la expresión, ésta se evalúa como [float](../../../csharp/language-reference/keywords/float.md) o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas.  
  
 Una expresión de punto flotante puede contener los siguientes conjuntos de valores:  
  
-   Cero negativo y positivo.  
  
-   Infinito positivo y negativo.  
  
-   Valor NaN \(no es un número\).  
  
-   El conjunto finito de valores distintos de cero.  
  
 Para obtener más información acerca de estos valores, consulte "IEEE Standard for Binary Floating\-Point Arithmetic" \(estándar IEEE para aritmética binaria de punto flotante\), que se encuentra disponible en el sitio web de [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).  
  
## Ejemplo  
 En el ejemplo siguiente, se suman valores [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) y `double` que dan un resultado `double`.  
  
 [!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de tipos de punto flotante](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)