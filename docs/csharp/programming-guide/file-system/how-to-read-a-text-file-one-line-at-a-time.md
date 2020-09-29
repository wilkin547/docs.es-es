---
title: 'Procedimiento para leer un archivo de texto de línea en línea: guía de programación de C#'
description: Aprenda a leer un archivo de texto línea a línea. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 93645ef78f1ceb3cc4cf1d20ac73112e86957293
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178520"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="d80e8-104">Procedimiento para leer un archivo de texto de línea en línea (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d80e8-104">How to read a text file one line at a time (C# Programming Guide)</span></span>

<span data-ttu-id="d80e8-105">En este ejemplo se lee el contenido de un archivo de texto línea a línea en una cadena mediante el método `ReadLine` de la clase `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="d80e8-105">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="d80e8-106">Cada línea de texto se almacena en la cadena `line` y se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d80e8-106">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d80e8-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d80e8-107">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="d80e8-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d80e8-108">Compiling the Code</span></span>  

 <span data-ttu-id="d80e8-109">Copie el código y péguelo en el método `Main` de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="d80e8-109">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="d80e8-110">Reemplace `"c:\test.txt"` por el nombre de archivo real.</span><span class="sxs-lookup"><span data-stu-id="d80e8-110">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d80e8-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d80e8-111">Robust Programming</span></span>  

 <span data-ttu-id="d80e8-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="d80e8-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d80e8-113">El archivo podría no existir.</span><span class="sxs-lookup"><span data-stu-id="d80e8-113">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="d80e8-114">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="d80e8-114">.NET Security</span></span>  

 <span data-ttu-id="d80e8-115">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d80e8-115">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="d80e8-116">Por ejemplo, es posible que el archivo `myFile.cs` no sea un archivo de código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="d80e8-116">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80e8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d80e8-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="d80e8-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d80e8-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d80e8-119">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d80e8-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
