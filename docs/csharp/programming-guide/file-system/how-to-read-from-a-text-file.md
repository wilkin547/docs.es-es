---
title: "Cómo: Leer de un archivo de texto (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2af6102ac6793b4612a6fbc41f8c50189cc24d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="53095-102">Cómo: Leer de un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="53095-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="53095-103">En este ejemplo se lee el contenido de un archivo de texto con los métodos estáticos <xref:System.IO.File.ReadAllText%2A> y <xref:System.IO.File.ReadAllLines%2A> de la clase <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53095-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="53095-104">Para obtener un ejemplo en el que se usa <xref:System.IO.StreamReader>, vea [Cómo: Leer un archivo de texto línea a línea](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="53095-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53095-105">Los archivos que se usan en este ejemplo se crean en el tema [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="53095-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53095-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53095-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53095-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="53095-107">Compiling the Code</span></span>  
 <span data-ttu-id="53095-108">Copie el código y péguelo en una aplicación de consola de C#.</span><span class="sxs-lookup"><span data-stu-id="53095-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="53095-109">Si no está usando los archivos de texto de [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), reemplace el argumento a `ReadAllText` y a `ReadAllLines` con la ruta de acceso adecuada y el nombre de archivo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="53095-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="53095-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="53095-110">Robust Programming</span></span>  
 <span data-ttu-id="53095-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="53095-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="53095-112">El archivo no existe o no existe en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="53095-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="53095-113">Compruebe la ruta de acceso y la ortografía del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="53095-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="53095-114">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="53095-114">.NET Framework Security</span></span>  
 <span data-ttu-id="53095-115">No confíe en el nombre de un archivo para determinar el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="53095-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="53095-116">Por ejemplo, el archivo `myFile.cs` puede que no sea un archivo de código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="53095-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53095-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="53095-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="53095-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="53095-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="53095-119">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="53095-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
