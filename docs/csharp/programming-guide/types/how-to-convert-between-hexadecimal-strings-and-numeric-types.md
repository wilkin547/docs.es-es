---
title: "Cómo: Convertir cadenas hexadecimales en tipos numéricos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
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
ms.openlocfilehash: 5852e79f551ce88e0ca54de159abbc222d769234
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Cómo: Convertir cadenas hexadecimales en tipos numéricos (Guía de programación de C#)
En estos ejemplos se muestra cómo realizar las tareas siguientes:  
  
-   Obtener el valor hexadecimal de cada uno de los caracteres de un elemento [string](../../../csharp/language-reference/keywords/string.md).  
  
-   Obtener el elemento [char](../../../csharp/language-reference/keywords/char.md) que corresponde a cada valor de una cadena hexadecimal.  
  
-   Convertir un elemento `string` hexadecimal en un elemento [int](../../../csharp/language-reference/keywords/int.md).  
  
-   Convertir un elemento `string` hexadecimal en un elemento [float](../../../csharp/language-reference/keywords/float.md).  
  
-   Convertir una matriz de [bytes](../../../csharp/language-reference/keywords/byte.md) en un elemento `string` hexadecimal.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se genera el valor hexadecimal de cada uno de los caracteres de `string`. Primero, analiza `string` como una matriz de caracteres. Después, llama a <xref:System.Convert.ToInt32%28System.Char%29> en cada uno de los caracteres para obtener su valor numérico. Finalmente, aplica formato al número como su representación hexadecimal en un elemento `string`.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se analiza un elemento `string` de valores hexadecimales y genera el carácter correspondiente a cada valor hexadecimal. Primero, llama al método [Split(Char\[\])](xref:System.String.Split(System.Char[])) para obtener cada valor hexadecimal como un elemento `string` individual en una matriz. Después, llama a <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> para convertir el valor hexadecimal en un valor decimal representado como un elemento [int](../../../csharp/language-reference/keywords/int.md). Muestra dos maneras distintas de obtener el carácter correspondiente a ese código de carácter. En la primera técnica se usa <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, que devuelve el carácter correspondiente al argumento de tipo entero como `string`. En la segunda técnica, `int` se convierte de manera explícita en un elemento [char](../../../csharp/language-reference/keywords/char.md).  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra otra manera de convertir un elemento `string` hexadecimal en un entero mediante la llamada al método <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo convertir un elemento `string` hexadecimal en un elemento [float](../../../csharp/language-reference/keywords/float.md) mediante la clase <xref:System.BitConverter?displayProperty=fullName> y el método <xref:System.Int32.Parse%2A?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo convertir una matriz de [bytes](../../../csharp/language-reference/keywords/byte.md) en una cadena hexadecimal mediante la clase <xref:System.BitConverter?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Cadenas con formato numérico estándar](http://msdn.microsoft.com/library/580e57eb-ac47-4ffd-bccd-3a1637c2f467)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [Cómo: Determinar si una cadena representa un valor numérico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

