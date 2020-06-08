---
title: 'Procedimiento Leer de un archivo de texto: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 8f79d22a86390ca931b05262e50865d852c154c7
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241752"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="64477-102">Procedimiento Leer de un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="64477-102">How to read from a text file (C# Programming Guide)</span></span>
<span data-ttu-id="64477-103">En este ejemplo se lee el contenido de un archivo de texto con los métodos estáticos <xref:System.IO.File.ReadAllText%2A> y <xref:System.IO.File.ReadAllLines%2A> de la clase <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64477-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
<span data-ttu-id="64477-104">Para obtener un ejemplo en el que se usa <xref:System.IO.StreamReader>, consulte [Procedimiento Leer un archivo de texto línea a línea](./how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="64477-104">For an example that uses <xref:System.IO.StreamReader>, see [How to read a text file one line at a time](./how-to-read-a-text-file-one-line-at-a-time.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="64477-105">Los archivos que se usan en este ejemplo se crean en el tema [Procedimiento Escribir en un archivo texto](./how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="64477-105">The files that are used in this example are created in the topic [How to write to a text file](./how-to-write-to-a-text-file.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="64477-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64477-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64477-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="64477-107">Compiling the Code</span></span>  
 <span data-ttu-id="64477-108">Copie el código y péguelo en una aplicación de consola de C#.</span><span class="sxs-lookup"><span data-stu-id="64477-108">Copy the code and paste it into a C# console application.</span></span>  
  
<span data-ttu-id="64477-109">Si no está usando los archivos de texto de [Procedimiento Escribir en un archivo texto](./how-to-write-to-a-text-file.md), reemplace el argumento a `ReadAllText` y a `ReadAllLines` por la ruta de acceso adecuada y el nombre de archivo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="64477-109">If you are not using the text files from [How to write to a text file](./how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>
  
## <a name="robust-programming"></a><span data-ttu-id="64477-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="64477-110">Robust Programming</span></span>  
 <span data-ttu-id="64477-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="64477-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="64477-112">El archivo no existe o no existe en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="64477-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="64477-113">Compruebe la ruta de acceso y la ortografía del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="64477-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="64477-114">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="64477-114">.NET Security</span></span>  
 <span data-ttu-id="64477-115">No confíe en el nombre de un archivo para determinar el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="64477-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="64477-116">Por ejemplo, el archivo `myFile.cs` puede que no sea un archivo de código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="64477-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64477-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="64477-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="64477-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="64477-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="64477-119">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="64477-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
