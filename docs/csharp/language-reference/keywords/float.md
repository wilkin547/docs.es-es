---
title: "float (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "float"
  - "float_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "float (palabra clave) [C#]"
  - "números de punto flotante [C#], float (palabra clave)"
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# float (Referencia de C#)
La palabra clave `float` denota un tipo simple que almacena valores de punto flotante de 32 bits.  La siguiente tabla muestra la precisión y el intervalo de valores aproximado para el tipo `float`.  
  
|Tipo|Intervalo aproximado|Precisión|Tipo de .NET Framework|  
|----------|--------------------------|---------------|----------------------------|  
|`float`|\-3.4 × 10<sup>38</sup>to \+3.4 × 10<sup>38</sup>|7 dígitos|<xref:System.Single?displayProperty=fullName>|  
  
## Literales  
 De forma predeterminada, un literal numérico real en el lado derecho del operador de asignación se trata como [double](../../../csharp/language-reference/keywords/double.md).  Por consiguiente, para inicializar una variable de tipo float, utilice el sufijo `f` o `F`, como en el ejemplo siguiente:  
  
```  
  
float x = 3.5F;  
```  
  
 Si no utiliza este sufijo en la declaración anterior, obtendrá un error de compilación, ya que está intentando almacenar un valor de tipo [double](../../../csharp/language-reference/keywords/double.md) en una variable de tipo `float`.  
  
## Conversiones  
 Es posible combinar tipos enteros numéricos y tipos de punto flotante en una expresión.  En este caso, los tipos enteros se convierten en tipos de punto flotante.  La evaluación de la expresión se realiza según las siguientes reglas:  
  
-   Si uno de los tipos de punto flotante es [double](../../../csharp/language-reference/keywords/double.md), la expresión se evalúa como [double](../../../csharp/language-reference/keywords/double.md) o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas.  
  
-   Si no existe ningún tipo [double](../../../csharp/language-reference/keywords/double.md) en la expresión, ésta se evalúa como `float` o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas.  
  
 Una expresión de punto flotante puede contener los siguientes conjuntos de valores:  
  
-   Cero negativo y positivo  
  
-   Infinito positivo y negativo  
  
-   Valor NaN \(no es un número\)  
  
-   El conjunto finito de valores distintos de cero  
  
 Para obtener más información acerca de estos valores, consulte "IEEE Standard for Binary Floating\-Point Arithmetic" \(estándar IEEE para aritmética binaria de punto flotante\), que se encuentra disponible en el sitio web de [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).  
  
## Ejemplo  
 En el siguiente ejemplo, una expresión matemática incluye valores de tipo [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md) y `float`, y proporciona un resultado de tipo `float`.  \(Recuerde que `float` es un alias para el tipo <xref:System.Single?displayProperty=fullName>.\) Observe que la expresión no incluye ningún valor de tipo [double](../../../csharp/language-reference/keywords/double.md).  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/csharp/float_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Single>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)