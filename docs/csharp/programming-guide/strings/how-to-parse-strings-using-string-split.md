---
title: "Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b97d1d89a4c74a4c759d1ed41a0bc2476b3b07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a>Cómo: Analizar cadenas mediante String.Split (Guía de programación de C#)
En el ejemplo de código siguiente se muestra cómo se puede analizar una consulta mediante el método <xref:System.String.Split%2A?displayProperty=nameWithType> . Como entrada, <xref:System.String.Split%2A> toma una matriz de caracteres que indica qué caracteres separan las cadenas sub interesantes de la cadena de destino.  La función devuelve una matriz de cadenas sub.  
  
 Este ejemplo usa espacios, comas, puntos, dos puntos y tabulaciones pasados en una matriz que contiene estos caracteres de separación <xref:System.String.Split%2A>.  Cada palabra de la frase de la cadena de destino se muestra por separado de la matriz de cadenas resultante.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 De forma predeterminada, String.Split devuelve las cadenas vacías cuando dos caracteres de separación aparecen de manera contigua en la cadena de destino.  Puede pasar un parámetro StringSplitOptions.RemoveEmptyEntries opcional para excluir las cadenas vacías en la salida.  
  
 String.Split puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
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
