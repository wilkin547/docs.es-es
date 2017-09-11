---
title: "Cómo: Leer de un archivo de texto (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- StreamReader.ReadToEnd
dev_langs:
- CSharp
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
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
ms.openlocfilehash: bd0ad3e062c4d4b32fb6140cacba9a4a32674759
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="8d682-102">Cómo: Leer de un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8d682-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="8d682-103">En este ejemplo se lee el contenido de un archivo de texto con los métodos estáticos <xref:System.IO.File.ReadAllText%2A> y <xref:System.IO.File.ReadAllLines%2A> de la clase <xref:System.IO.File?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8d682-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="8d682-104">Para obtener un ejemplo en el que se usa <xref:System.IO.StreamReader>, vea [Cómo: Leer un archivo de texto línea a línea](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="8d682-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d682-105">Los archivos que se usan en este ejemplo se crean en el tema [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="8d682-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d682-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d682-106">Example</span></span>  
 <span data-ttu-id="8d682-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8d682-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d682-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8d682-108">Compiling the Code</span></span>  
 <span data-ttu-id="8d682-109">Copie el código y péguelo en una aplicación de consola de C#.</span><span class="sxs-lookup"><span data-stu-id="8d682-109">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="8d682-110">Si no está usando los archivos de texto de [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), reemplace el argumento a `ReadAllText` y a `ReadAllLines` con la ruta de acceso adecuada y el nombre de archivo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8d682-110">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8d682-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8d682-111">Robust Programming</span></span>  
 <span data-ttu-id="8d682-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="8d682-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8d682-113">El archivo no existe o no existe en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="8d682-113">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="8d682-114">Compruebe la ruta de acceso y la ortografía del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="8d682-114">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8d682-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8d682-115">.NET Framework Security</span></span>  
 <span data-ttu-id="8d682-116">No confíe en el nombre de un archivo para determinar el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="8d682-116">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="8d682-117">Por ejemplo, el archivo `myFile.cs` puede que no sea un archivo de código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="8d682-117">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d682-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d682-118">See Also</span></span>  
 <span data-ttu-id="8d682-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8d682-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="8d682-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d682-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8d682-121">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8d682-121">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

