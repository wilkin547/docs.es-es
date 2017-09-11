---
title: "Cómo: Escribir en un archivo de texto (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
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
ms.openlocfilehash: 12a74a5664a8f514c89d9de3ce470c98319f84d2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="a57d1-102">Cómo: Escribir en un archivo de texto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a57d1-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="a57d1-103">En estos ejemplos se muestran varias formas de escribir texto en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a57d1-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="a57d1-104">Los dos primeros ejemplos usan métodos estáticos convenientes en la clase <xref:System.IO.File?displayProperty=fullName> para escribir cada elemento de cualquier IEnumerable\<string> y una cadena en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a57d1-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=fullName> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="a57d1-105">En el ejemplo 3 se muestra cómo agregar texto a un archivo cuando es necesario procesar cada línea individualmente a medida que se escribe en el archivo.</span><span class="sxs-lookup"><span data-stu-id="a57d1-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="a57d1-106">Los ejemplos 1-3 sobrescriben todo el contenido del archivo, pero el ejemplo 4 muestra cómo anexar texto a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="a57d1-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="a57d1-107">En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.</span><span class="sxs-lookup"><span data-stu-id="a57d1-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="a57d1-108">También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="a57d1-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a57d1-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a57d1-109">Example</span></span>  
 <span data-ttu-id="a57d1-110">[!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a57d1-110">[!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]</span></span>  
  
 <span data-ttu-id="a57d1-111">En todos estos ejemplos se escriben literales de cadena en los archivos, pero es más conveniente utilizar el método <xref:System.String.Format%2A>, que tiene muchos controles para escribir diferentes tipos de valores alineados a la derecha o a la izquierda en un campo, con o sin relleno, etc.</span><span class="sxs-lookup"><span data-stu-id="a57d1-111">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="a57d1-112">También puede usar la característica de [interpolación de cadenas](../../../csharp/language-reference/keywords/interpolated-strings.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="a57d1-112">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a57d1-113">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a57d1-113">Robust Programming</span></span>  
 <span data-ttu-id="a57d1-114">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a57d1-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a57d1-115">El archivo ya existe y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a57d1-115">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="a57d1-116">Puede que el nombre de ruta de acceso sea demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="a57d1-116">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="a57d1-117">Es posible que el disco esté lleno.</span><span class="sxs-lookup"><span data-stu-id="a57d1-117">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57d1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a57d1-118">See Also</span></span>  
 <span data-ttu-id="a57d1-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a57d1-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a57d1-120">[Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="a57d1-120">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 [<span data-ttu-id="a57d1-121">Ejemplo: guardar una colección en el almacenamiento para la aplicación</span><span class="sxs-lookup"><span data-stu-id="a57d1-121">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)

