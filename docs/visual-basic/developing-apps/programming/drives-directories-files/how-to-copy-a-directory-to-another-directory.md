---
title: 'Cómo: Copiar un directorio en otro directorio'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
ms.openlocfilehash: a23079f093f53ab8e20eb71c684a594dcf7f894b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348864"
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="a4e73-102">Cómo: Copiar un directorio en otro directorio en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a4e73-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>

<span data-ttu-id="a4e73-103">Use el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> para copiar un directorio en otro directorio.</span><span class="sxs-lookup"><span data-stu-id="a4e73-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="a4e73-104">Este método copia el contenido del directorio además del propio directorio.</span><span class="sxs-lookup"><span data-stu-id="a4e73-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="a4e73-105">Si el directorio de destino no existe, se creará.</span><span class="sxs-lookup"><span data-stu-id="a4e73-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="a4e73-106">Si existe un directorio con el mismo nombre en la ubicación de destino y `overwrite` se establece en `False`, se combinará el contenido de los dos directorios.</span><span class="sxs-lookup"><span data-stu-id="a4e73-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="a4e73-107">Puede especificar un nuevo nombre para el directorio durante la operación.</span><span class="sxs-lookup"><span data-stu-id="a4e73-107">You can specify a new name for the directory during the operation.</span></span>

<span data-ttu-id="a4e73-108">Al copiar archivos en un directorio, pueden iniciarse excepciones producidas por un archivo concreto, como un archivo existente durante una combinación mientras `overwrite` está establecido en `False`.</span><span class="sxs-lookup"><span data-stu-id="a4e73-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="a4e73-109">Cuando estas excepciones se inician, se consolidan en una sola excepción, cuya propiedad `Data` contiene entradas en las que la ruta de acceso del archivo o directorio es la clave y el mensaje de excepción concreto está contenido en el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a4e73-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>

## <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="a4e73-110">Para copiar un directorio en otro</span><span class="sxs-lookup"><span data-stu-id="a4e73-110">To copy a directory to another directory</span></span>

- <span data-ttu-id="a4e73-111">Use el método `CopyDirectory` y especifique los nombres de los directorios de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="a4e73-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="a4e73-112">En el ejemplo siguiente se copia el directorio denominado `TestDirectory1` en `TestDirectory2`, lo que sobrescribe los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a4e73-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>

    [!code-vb[VbVbcnMyFileSystem#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#16)]

    <span data-ttu-id="a4e73-113">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a4e73-113">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a4e73-114">En el selector de fragmentos de código, se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**.</span><span class="sxs-lookup"><span data-stu-id="a4e73-114">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="a4e73-115">Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="a4e73-115">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>

## <a name="robust-programming"></a><span data-ttu-id="a4e73-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a4e73-116">Robust Programming</span></span>

<span data-ttu-id="a4e73-117">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a4e73-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="a4e73-118">El nuevo nombre especificado para el directorio contiene un signo de dos puntos (:) o una barra diagonal (\ o /) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-118">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="a4e73-119">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="a4e73-120">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="a4e73-121">`destinationDirectoryName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="a4e73-121">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>

- <span data-ttu-id="a4e73-122">El directorio de origen no existe (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-122">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="a4e73-123">El directorio de origen es un directorio raíz (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-123">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="a4e73-124">La ruta de acceso combinada apunta a un archivo existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-124">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="a4e73-125">Las rutas de acceso de origen y destino son iguales (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-125">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="a4e73-126">`ShowUI` se establece en `UIOption.AllDialogs` y el usuario cancela la operación o uno o más archivos del directorio no pueden copiarse (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-126">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>

- <span data-ttu-id="a4e73-127">La operación es cíclica (<xref:System.InvalidOperationException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-127">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>

- <span data-ttu-id="a4e73-128">La ruta de acceso contiene un signo de dos puntos (:) (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-128">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="a4e73-129">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-129">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="a4e73-130">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-130">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="a4e73-131">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-131">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="a4e73-132">Un archivo de destino existe pero no se puede acceder a él (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="a4e73-132">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="a4e73-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4e73-133">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>
- [<span data-ttu-id="a4e73-134">Buscar subdirectorios con un modelo concreto</span><span class="sxs-lookup"><span data-stu-id="a4e73-134">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)
- [<span data-ttu-id="a4e73-135">Obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="a4e73-135">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
