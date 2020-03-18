---
title: 'Procedimiento Escribir en un archivo de texto: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ac16fb971eae5654a55e2f1753d78a6458f03315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712252"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="37239-102">Procedimiento Escribir en un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="37239-102">How to write to a text file (C# Programming Guide)</span></span>
<span data-ttu-id="37239-103">En estos ejemplos se muestran varias formas de escribir texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="37239-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="37239-104">Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier `IEnumerable<string>` y una cadena en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="37239-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="37239-105">En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.</span><span class="sxs-lookup"><span data-stu-id="37239-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="37239-106">Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="37239-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="37239-107">Todos estos ejemplos escriben literales de cadena en los archivos.</span><span class="sxs-lookup"><span data-stu-id="37239-107">These examples all write string literals to files.</span></span> <span data-ttu-id="37239-108">Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="37239-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37239-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37239-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="37239-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="37239-110">Robust Programming</span></span>  
 <span data-ttu-id="37239-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="37239-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="37239-112">El archivo ya existe y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="37239-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="37239-113">Puede que el nombre de ruta de acceso sea demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="37239-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="37239-114">Es posible que el disco esté lleno.</span><span class="sxs-lookup"><span data-stu-id="37239-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37239-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="37239-115">See also</span></span>

- [<span data-ttu-id="37239-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="37239-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="37239-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="37239-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="37239-118">Ejemplo: guardar una colección en el almacenamiento para la aplicación</span><span class="sxs-lookup"><span data-stu-id="37239-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
