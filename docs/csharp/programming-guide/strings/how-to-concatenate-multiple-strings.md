---
title: "Cómo: Concatenar varias cadenas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a>Cómo: Concatenar varias cadenas (Guía de programación de C#)
*Concatenación* es el proceso de anexar una cadena al final de otra cadena. Cuando concatena literales de cadena o constantes de cadena con el operador `+`, el compilador crea una cadena única. No se produce ninguna concatenación en tiempo de ejecución. En cambio, las variables de cadena pueden concatenarse solo en tiempo de ejecución. En este caso, debe entender las implicaciones de rendimiento de los diversos enfoques.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad en el código fuente. Estas partes se concatenarán en una sola cadena en tiempo de compilación. No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas implicadas.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, o los métodos <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>. El operador `+` es sencillo de usar y genera un código intuitivo. Incluso si usa varios operadores + en una instrucción, el contenido de la cadena se copia solo una vez. Pero si repite esta operación varias veces, por ejemplo en un bucle, puede provocar problemas de eficacia. Por ejemplo, observe el código siguiente:  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía, pero no convierte el valor de la cadena NULL original.  
  
 Si no está concatenando un gran número de cadenas (por ejemplo, en un bucle), el costo de rendimiento de este código probablemente no sea significante. Lo mismo se cumple para los métodos <xref:System.String.Concat%2A?displayProperty=fullName> y <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 En cambio, cuando el rendimiento es importante, siempre debe usar la clase <xref:System.Text.StringBuilder> para concatenar cadenas. En el código siguiente se usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas sin el efecto de encadenamiento del operador `+`.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)

