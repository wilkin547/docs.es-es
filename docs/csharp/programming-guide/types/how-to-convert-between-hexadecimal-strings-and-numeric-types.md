---
title: "C&#243;mo: Convertir cadenas hexadecimales en tipos num&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversiones [C#], cadenas hexadecimales"
  - "cadenas hexadecimales [C#]"
  - "cadenas hexadecimales [C#], convertir a tipo numérico"
  - "cadenas [C#], convertir cadenas hexadecimales"
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Convertir cadenas hexadecimales en tipos num&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En estos ejemplos se muestra cómo realizar las tareas siguientes:  
  
-   Obtener el valor hexadecimal de cada uno de los caracteres de un elemento [string](../../../csharp/language-reference/keywords/string.md).  
  
-   Obtener el elemento [char](../../../csharp/language-reference/keywords/char.md) que corresponde a cada valor en una cadena hexadecimal.  
  
-   Convertir un elemento `string` hexadecimal en un elemento [int](../../../csharp/language-reference/keywords/int.md).  
  
-   Convertir un elemento `string` hexadecimal en un elemento [float](../../../csharp/language-reference/keywords/float.md).  
  
-   Convertir una matriz de [bytes](../../../csharp/language-reference/keywords/byte.md) en un elemento `string` hexadecimal.  
  
## Ejemplo  
 Este ejemplo genera el valor hexadecimal de cada uno de los caracteres de `string`.  Primero, analiza `string` como una matriz de caracteres.  Después, llama a <xref:System.Convert.ToInt32%28System.Char%29> en cada uno de los caracteres para obtener sus respectivos valores numéricos.  Finalmente, da formato al número como su representación hexadecimal en `string`.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## Ejemplo  
 Este ejemplo analiza una `string` de valores hexadecimales y genera el carácter correspondiente a cada valor hexadecimal.  Primero, llama al método [Split\(Char\[\]\)](assetId:///M:System.String.Split(System.Char[])?qualifyHint=False&autoUpgrade=False) para obtener cada valor hexadecimal como una `string` individual en una matriz.  A continuación, llama a <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> para convertir el valor hexadecimal en un valor decimal representado como un valor de tipo [int](../../../csharp/language-reference/keywords/int.md).  Muestra dos formas distintas de obtener el carácter correspondiente a ese código de carácter.  En la primera técnica, se utiliza el método <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, que devuelve el carácter correspondiente al argumento de tipo entero como `string`.  En la segunda técnica, `int` se convierte de forma explícita en un valor de tipo [char](../../../csharp/language-reference/keywords/char.md).  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## Ejemplo  
 Este ejemplo muestra otra forma de convertir una `string` hexadecimal en un entero, que consiste en llamar al método <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo convertir un elemento `string` hexadecimal en un elemento [float](../../../csharp/language-reference/keywords/float.md) mediante la clase <xref:System.BitConverter?displayProperty=fullName> y el método <xref:System.Int32.Parse%2A?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo convertir una matriz de [bytes](../../../csharp/language-reference/keywords/byte.md) en una cadena hexadecimal mediante la clase <xref:System.BitConverter?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## Vea también  
 [Cadenas con formato numérico estándar](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [Cómo: Determinar si una cadena representa un valor numérico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)