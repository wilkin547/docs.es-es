---
title: "Cómo: Escribir en un archivo de texto (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="0de0c-102">Cómo: Escribir en un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0de0c-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="0de0c-103">En estos ejemplos se muestran varias formas de escribir texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0de0c-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="0de0c-104">Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=nameWithType> para escribir cada elemento de cualquier IEnumerable\<string> y una cadena en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0de0c-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="0de0c-105">En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.</span><span class="sxs-lookup"><span data-stu-id="0de0c-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="0de0c-106">Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="0de0c-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="0de0c-107">En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.</span><span class="sxs-lookup"><span data-stu-id="0de0c-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="0de0c-108">También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="0de0c-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de0c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0de0c-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 <span data-ttu-id="0de0c-110">En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.</span><span class="sxs-lookup"><span data-stu-id="0de0c-110">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="0de0c-111">También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="0de0c-111">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0de0c-112">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="0de0c-112">Robust Programming</span></span>  
 <span data-ttu-id="0de0c-113">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="0de0c-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0de0c-114">El archivo ya existe y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0de0c-114">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="0de0c-115">Puede que el nombre de ruta de acceso sea demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="0de0c-115">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="0de0c-116">Es posible que el disco esté lleno.</span><span class="sxs-lookup"><span data-stu-id="0de0c-116">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de0c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0de0c-117">See Also</span></span>  
 [<span data-ttu-id="0de0c-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0de0c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0de0c-119">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0de0c-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="0de0c-120">Ejemplo: guardar una colección en el almacenamiento para la aplicación</span><span class="sxs-lookup"><span data-stu-id="0de0c-120">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
