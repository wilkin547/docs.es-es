---
title: "sizeof (Referencia de C#) | Microsoft Docs"
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
  - "sizeof_CSharpKeyword"
  - "sizeof"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sizeof (palabra clave) [C#]"
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# sizeof (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se usa para obtener el tamaño en bytes de un tipo no administrado.  Los tipos no administrados incluyen los tipos integrados que se muestran en la tabla que figura a continuación, además de estos:  
  
-   Tipos de enumeración  
  
-   Tipos de puntero  
  
-   Structs definidos por el usuario que no contienen ningún campo o propiedad que sea un tipo de referencia  
  
 En el ejemplo siguiente, se muestra cómo recuperar el tamaño de un valor de tipo `int`:  
  
```c#  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## Comentarios  
 A partir de la versión 2.0 de C\#, la aplicación de `sizeof` a los tipos integrados ya no requiere el uso del modo [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 El operador `sizeof` no se puede sobrecargar.  Los valores devueltos por el operador `sizeof` son del tipo `int`.  En la tabla siguiente, se muestran los valores constantes que se sustituyen por expresiones `sizeof` que tienen determinados tipos integrados como operandos.  
  
|Expresión|Valor constante|  
|---------------|---------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 \(Unicode\)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Para todos los demás tipos, incluidos los structs, el operador `sizeof` se puede usar únicamente en bloques de código no seguro.  Si bien se puede usar el método <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>, el valor devuelto por este método no siempre es idéntico al valor devuelto por `sizeof`.  <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> devuelve el tamaño una vez calculadas las referencias del tipo, mientras que `sizeof` devuelve el tamaño asignado por Common Language Runtime, incluido el relleno.  
  
## Ejemplo  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)