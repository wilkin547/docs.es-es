---
title: 'Procedimiento para leer un archivo de texto de línea en línea: guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: e4a9ba2da2548991f442c2f5ab09d39243137875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167525"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="d50b2-102">Procedimiento para leer un archivo de texto de línea en línea (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d50b2-102">How to read a text file one line at a time (C# Programming Guide)</span></span>
<span data-ttu-id="d50b2-103">En este ejemplo se lee el contenido de un archivo de texto línea a línea en una cadena mediante el método `ReadLine` de la clase `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="d50b2-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="d50b2-104">Cada línea de texto se almacena en la cadena `line` y se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d50b2-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d50b2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d50b2-105">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d50b2-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d50b2-106">Compiling the Code</span></span>  
 <span data-ttu-id="d50b2-107">Copie el código y péguelo en el método `Main` de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="d50b2-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="d50b2-108">Reemplace `"c:\test.txt"` por el nombre de archivo real.</span><span class="sxs-lookup"><span data-stu-id="d50b2-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d50b2-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d50b2-109">Robust Programming</span></span>  
 <span data-ttu-id="d50b2-110">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="d50b2-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d50b2-111">El archivo podría no existir.</span><span class="sxs-lookup"><span data-stu-id="d50b2-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d50b2-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d50b2-112">.NET Framework Security</span></span>  
 <span data-ttu-id="d50b2-113">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d50b2-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="d50b2-114">Por ejemplo, es posible que el archivo `myFile.cs` no sea un archivo de código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="d50b2-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50b2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d50b2-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="d50b2-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d50b2-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d50b2-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d50b2-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
