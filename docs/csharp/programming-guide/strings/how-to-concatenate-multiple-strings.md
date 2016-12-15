---
title: "C&#243;mo: Concatenar varias cadenas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "concatenación de cadenas [C#]"
  - "unión de cadenas [C#]"
  - "cadenas [C#], concatenación"
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Concatenar varias cadenas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La *concatenación* es el proceso de anexar una cadena al final de otra cadena.  Al concatenar literales o constantes de cadena mediante el operador `+`, el compilador crea una única cadena.  No se produce la concatenación en tiempo de ejecución.  Sin embargo, las variables de cadena sólo pueden concatenarse en tiempo de ejecución.  En este caso, debe entender las implicaciones de rendimiento de los distintos enfoques.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo dividir un literal de cadena largo en cadenas más pequeñas a fin de mejorar la legibilidad en el código fuente.  Estas partes se concatenarán en una única cadena en tiempo de compilación.  El rendimiento no se ve afectado en tiempo de ejecución, independiente del número de cadenas implicadas.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## Ejemplo  
 Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, o los métodos <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> u <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.  El operador `+` es fácil de utilizar y hace que el código resulte intuitivo.  Aunque se utilicen varios operadores \+ en una instrucción, el contenido de la cadena se copia una vez sola vez.  Pero si repite esta operación varias veces, por ejemplo, en un bucle, podría dar lugar a problemas de eficacia.  Por ejemplo, tenga en cuenta el código siguiente:  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  En las operaciones de concatenación de cadenas, el compilador de C\# trata una cadena nula de la misma forma que una cadena vacía, pero no convierte el valor de la cadena nula original.  
  
 Si no va a concatenar un gran número de cadenas \(por ejemplo, en un bucle\), probablemente el costo para el rendimiento de este código no sea significativo.  Lo anterior también se aplica a los métodos <xref:System.String.Concat%2A?displayProperty=fullName> y <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 Sin embargo, cuando el rendimiento es importante, debería utilizar siempre la clase <xref:System.Text.StringBuilder> para concatenar cadenas.  En el código siguiente se utiliza el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas sin el efecto de encadenamiento del operador `+`.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## Vea también  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)