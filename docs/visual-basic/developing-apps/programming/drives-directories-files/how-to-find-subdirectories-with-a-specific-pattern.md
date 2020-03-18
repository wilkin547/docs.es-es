---
title: 'Cómo: Buscar subdirectorios con un modelo concreto'
ms.date: 07/20/2015
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
ms.openlocfilehash: c8e13598080139cafabffb2e17d0a3b99c37dc5d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348770"
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="a868f-102">Cómo: Buscar subdirectorios con un modelo concreto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a868f-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>

<span data-ttu-id="a868f-103">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> devuelve una colección de solo lectura de cadenas que representan los nombres de ruta de acceso de los subdirectorios de un directorio.</span><span class="sxs-lookup"><span data-stu-id="a868f-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="a868f-104">Puede usar el parámetro `wildCards` para especificar un patrón concreto.</span><span class="sxs-lookup"><span data-stu-id="a868f-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="a868f-105">Si quiere incluir el contenido de subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.</span><span class="sxs-lookup"><span data-stu-id="a868f-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>

<span data-ttu-id="a868f-106">Se devuelve una colección vacía si no se encuentra ningún directorio que coincida con el modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="a868f-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>

## <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="a868f-107">Para buscar subdirectorios con un modelo concreto</span><span class="sxs-lookup"><span data-stu-id="a868f-107">To find subdirectories with a specific pattern</span></span>

<span data-ttu-id="a868f-108">Use el método `GetDirectories` y proporcione el nombre y ruta de acceso del directorio que quiera buscar.</span><span class="sxs-lookup"><span data-stu-id="a868f-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="a868f-109">En el ejemplo siguiente se devuelven todos los directorios de la estructura de directorios que contienen la palabra "Logs" en su nombre y se agregan a `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="a868f-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>

[!code-vb[VbVbcnFileAccess#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnFileAccess/VB/Class1.vb#1)]

## <a name="robust-programming"></a><span data-ttu-id="a868f-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a868f-110">Robust Programming</span></span>

<span data-ttu-id="a868f-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a868f-111">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="a868f-112">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="a868f-113">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="a868f-114">Uno (o más) de los caracteres comodín especificados es `Nothing`, una cadena vacía o contiene solo espacios (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-114">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="a868f-115">`directory` no existe (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="a868f-116">`directory` apunta a un archivo existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="a868f-117">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="a868f-118">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="a868f-119">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="a868f-120">El usuario no tiene los permisos necesarios (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="a868f-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="a868f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a868f-121">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>
- [<span data-ttu-id="a868f-122">Buscar archivos con un modelo concreto</span><span class="sxs-lookup"><span data-stu-id="a868f-122">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
