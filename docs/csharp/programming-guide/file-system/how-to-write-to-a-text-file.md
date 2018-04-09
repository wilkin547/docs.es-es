---
title: 'Cómo: Escribir en un archivo de texto (Guía de programación de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fa6de76e3981e0f05b5b192045043422a8a912aa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="b77a3-102">Cómo: Escribir en un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b77a3-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="b77a3-103">En estos ejemplos se muestran varias formas de escribir texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b77a3-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="b77a3-104">Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier `IEnumerable<string>` y una cadena en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b77a3-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="b77a3-105">En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.</span><span class="sxs-lookup"><span data-stu-id="b77a3-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="b77a3-106">Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="b77a3-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="b77a3-107">Todos estos ejemplos escriben literales de cadena en los archivos.</span><span class="sxs-lookup"><span data-stu-id="b77a3-107">These examples all write string literals to files.</span></span> <span data-ttu-id="b77a3-108">Si quiere aplicar formato al texto escrito en un archivo, use el método <xref:System.String.Format%2A> o la característica [interpolación de cadenas](../../../csharp/language-reference/tokens/interpolated.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="b77a3-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../../csharp/language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b77a3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b77a3-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b77a3-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b77a3-110">Robust Programming</span></span>  
 <span data-ttu-id="b77a3-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="b77a3-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b77a3-112">El archivo ya existe y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b77a3-112">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="b77a3-113">Puede que el nombre de ruta de acceso sea demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="b77a3-113">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="b77a3-114">Es posible que el disco esté lleno.</span><span class="sxs-lookup"><span data-stu-id="b77a3-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77a3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b77a3-115">See Also</span></span>  
 [<span data-ttu-id="b77a3-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b77a3-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b77a3-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b77a3-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="b77a3-118">Ejemplo: guardar una colección en el almacenamiento para la aplicación</span><span class="sxs-lookup"><span data-stu-id="b77a3-118">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
