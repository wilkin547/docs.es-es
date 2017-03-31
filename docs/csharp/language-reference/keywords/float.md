---
title: float (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1c3a66e4f9c690effb35e280e00e29930ec64d75
ms.lasthandoff: 03/13/2017

---
# <a name="float-c-reference"></a>float (Referencia de C#)
La palabra clave `float` indica un tipo simple que almacena valores de punto flotante de 32 bits. En la tabla siguiente se muestran la precisión y el intervalo aproximado para el tipo `float`.  
  
|Tipo|Intervalo aproximado|Precisión|Tipo de .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|De -3,4 × 10<sup>38</sup>a +3,4 × 10<sup>38</sup>|7 dígitos|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  
 De forma predeterminada, un literal numérico real a la derecha del operador de asignación se trata como [double](double.md). Por consiguiente, para inicializar una variable float, use el sufijo `f` o `F`, como en el ejemplo siguiente:  
  
```csharp
float x = 3.5F;  
```
  
 Si no usa el sufijo en la declaración anterior, obtendrá un error de compilación porque intenta almacenar un valor [double](double.md) en una variable `float`.  
  
## <a name="conversions"></a>Conversiones  
 Puede combinar tipos numéricos enteros y tipos de punto flotante en una expresión. En este caso, los tipos enteros se convierten a tipos de punto flotante. La evaluación de la expresión se realiza según las reglas siguientes:  
  
-   Si uno de los tipos de punto flotante es [double](double.md), la expresión se evalúa como [double](double.md) o [bool](bool.md) en expresiones relacionales o booleanas.  
  
-   Si no hay ningún tipo [double](double.md) en la expresión, esta se evalúa como `float` o [bool](bool.md) en expresiones relacionales o booleanas.  
  
 Una expresión de punto flotante puede contener los siguientes conjuntos de valores:  
  
-   Cero positivo y negativo  
  
-   Infinito positivo y negativo  
  
-   Valor no numérico (NaN)  
  
-   El conjunto finito de valores distintos de cero  
  
 Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se incluyen un [int](int.md), un [short](short.md) y un `float` en una expresión matemática cuyo resultado es `float`. (Recuerde que `float` es un alias del tipo <xref:System.Single?displayProperty=fullName>). Observe que no hay ningún [double](double.md) en la expresión.  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Single>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])  
 [Palabras clave de C#](index.md)   
 [Integral Types Table](integral-types-table.md)  (Tabla de tipos enteros)  
 [Built-In Types Table](built-in-types-table.md)  (Tabla de tipos integrados)  
 [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)
