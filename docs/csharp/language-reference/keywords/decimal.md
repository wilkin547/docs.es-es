---
title: "decimal (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "decimal_CSharpKeyword"
  - "decimal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "decimal (palabra clave) [C#]"
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 32
---
# decimal (Referencia de C#)
La palabra clave `decimal` indica un tipo de datos de 128 bits.  Comparado con los tipos de punto flotante, el tipo `decimal` tiene una mayor precisión y un intervalo más reducido, lo que lo hace adecuado para los cálculos financieros y monetarios.  El intervalo aproximado y la precisión para el tipo `decimal` se muestran en la siguiente tabla.  
  
|Tipo|Intervalo aproximado|Precisión|Tipo de .NET Framework|  
|----------|--------------------------|---------------|----------------------------|  
|`decimal`|\(de \-7,9 x 10<sup>28</sup> a 7,9 x 10<sup>28</sup>\) \/ \(10<sup>0 a 28</sup>\)|28\-29 dígitos significativos|<xref:System.Decimal?displayProperty=fullName>|  
  
## Literales  
 Si desea que un literal real numérico se trate como `decimal`, use el sufijo m o M; por ejemplo:  
  
```  
  
decimal myMoney = 300.5m;  
```  
  
 Sin el sufijo m, el número se trata como [double](../../../csharp/language-reference/keywords/double.md) y genera un error del compilador.  
  
## Conversiones  
 Los tipos enteros se convierten implícitamente en `decimal` y el resultado se evalúa como `decimal`.  Por consiguiente, es posible inicializar una variable decimal mediante un literal entero, sin el sufijo, de la manera siguiente:  
  
```  
  
decimal myMoney = 300;  
```  
  
 No hay una conversión implícita entre los tipos de punto flotante y el tipo `decimal`; por lo tanto, se debe usar una conversión entre ambos.  Por ejemplo:  
  
```  
  
        decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 Asimismo, puede mezclar `decimal` y tipos enteros numéricos en la misma expresión.  No obstante, al mezclar `decimal` y tipos de punto flotante sin una conversión se produce un error de compilación.  
  
 Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## Aplicar formato a resultados decimales  
 Puede aplicar formato a los resultados mediante el método `String.Format` o a través del método <xref:System.Console.Write%2A?displayProperty=fullName>, que llama a `String.Format()`.  El formato de divisa se especifica mediante la cadena de formato de divisa estándar "C" o "c", como se muestra en el segundo ejemplo más adelante en este artículo.  Para obtener más información sobre el método `String.Format`, vea <xref:System.String.Format%2A?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente se genera un error del compilador al intentar agregar las variables [double](../../../csharp/language-reference/keywords/double.md) y `decimal`.  
  
```c#  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
  
```  
  
 El resultado es el siguiente error:  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 En este ejemplo, `decimal` e [int](../../../csharp/language-reference/keywords/int.md) se mezclan en la misma expresión.  El resultado se evalúa como tipo `decimal`.  
  
 [!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/csharp/decimal_1.cs)]  
  
## Ejemplo  
 En este ejemplo, se da formato a los resultados mediante la cadena de formato de divisa.  Observe que `x` se redondea, ya que las posiciones decimales superan 0,99 $.  La variable `y`, que representa el máximo de dígitos exactos, se muestra exactamente en el formato correcto.  
  
 [!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/csharp/decimal_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Decimal>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Cadenas con formato numérico estándar](../Topic/Standard%20Numeric%20Format%20Strings.md)