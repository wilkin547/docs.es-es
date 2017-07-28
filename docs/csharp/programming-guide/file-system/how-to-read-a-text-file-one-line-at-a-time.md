---
title: "Cómo: Leer un archivo de texto línea a línea (Visual C#) |"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
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
ms.openlocfilehash: e9327181d82a97559c7be99bb76a2a93118d796b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Cómo: Leer un archivo de texto línea a línea (Visual C#) |
En este ejemplo se lee el contenido de un archivo de texto línea a línea en una cadena mediante el método `ReadLine` de la clase `StreamReader`. Cada línea de texto se almacena en la cadena `line` y se muestra en la pantalla.  
  
## <a name="example"></a>Ejemplo  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código y péguelo en el método `Main` de una aplicación de consola.  
  
 Reemplace `"c:\test.txt"` por el nombre de archivo real.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo podría no existir.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo `myFile.cs` no sea un archivo de código fuente de C#.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)

