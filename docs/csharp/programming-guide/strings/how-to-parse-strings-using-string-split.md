---
title: "Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0ef96f1cb074c32208457c192d53c69d95a102d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a>Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)
En el ejemplo de código siguiente se muestra cómo se puede analizar una consulta mediante el método <xref:System.String.Split%2A?displayProperty=fullName> . Como entrada, <xref:System.String.Split%2A> toma una matriz de caracteres que indica qué caracteres separan las cadenas sub interesantes de la cadena de destino.  La función devuelve una matriz de cadenas sub.  
  
 Este ejemplo usa espacios, comas, puntos, dos puntos y tabulaciones pasados en una matriz que contiene estos caracteres de separación <xref:System.String.Split%2A>.  Cada palabra de la frase de la cadena de destino se muestra por separado de la matriz de cadenas resultante.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 De forma predeterminada, String.Split devuelve las cadenas vacías cuando dos caracteres de separación aparecen de manera contigua en la cadena de destino.  Puede pasar un parámetro StringSplitOptions.RemoveEmptyEntries opcional para excluir las cadenas vacías en la salida.  
  
 String.Split puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        char[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312)

