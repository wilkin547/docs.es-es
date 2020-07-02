---
title: Archivos asignados a memoria
description: Explore los archivos asignados a memoria en .NET, que mantienen el contenido de los archivos en la memoria virtual, y permita que las aplicaciones modifiquen el archivo escribiendo directamente en la memoria.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
ms.openlocfilehash: db63c15357b0670c55b1174b91b02e2f49a0c4c1
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661984"
---
# <a name="memory-mapped-files"></a><span data-ttu-id="646ea-103">Archivos asignados a memoria</span><span class="sxs-lookup"><span data-stu-id="646ea-103">Memory-Mapped Files</span></span>
<span data-ttu-id="646ea-104">Un archivo asignado a memoria incluye el contenido de un archivo en la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="646ea-104">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="646ea-105">Esta asignación entre un archivo y el espacio de memoria permite a una aplicación, incluidos varios procesos, modificar el archivo leyendo y escribiendo directamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-105">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="646ea-106">A partir de .NET Framework 4, se puede usar código administrado para tener acceso a los archivos asignados a memoria del mismo modo que las funciones nativas de Windows tienen acceso a los archivos asignados a memoria, tal como se describe en [Administración de archivos asignados a memoria](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="646ea-106">Starting with the .NET Framework 4, you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="646ea-107">Hay dos tipos de archivos asignados a memoria:</span><span class="sxs-lookup"><span data-stu-id="646ea-107">There are two types of memory-mapped files:</span></span>  
  
- <span data-ttu-id="646ea-108">Archivos asignados a memoria persistentes</span><span class="sxs-lookup"><span data-stu-id="646ea-108">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="646ea-109">Los archivos persistentes son archivos asignados a memoria que están asociados a un archivo de origen ubicado en un disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-109">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="646ea-110">Cuando el último proceso termina de usar el archivo, los datos se guardan en el archivo de origen ubicado en el disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-110">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="646ea-111">Estos archivos asignados a memoria son idóneos para trabajar con archivos de origen muy grandes.</span><span class="sxs-lookup"><span data-stu-id="646ea-111">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
- <span data-ttu-id="646ea-112">Archivos asignados a memoria no persistentes</span><span class="sxs-lookup"><span data-stu-id="646ea-112">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="646ea-113">Los archivos no persistentes son archivos asignados a memoria que no están asociados a un archivo ubicado en un disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-113">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="646ea-114">Cuando el último proceso termina de usar el archivo, se pierden los datos y la recolección de elementos no utilizados reclama el archivo.</span><span class="sxs-lookup"><span data-stu-id="646ea-114">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="646ea-115">Estos archivos son idóneos para crear memoria compartida para las comunicaciones entre procesos (IPC).</span><span class="sxs-lookup"><span data-stu-id="646ea-115">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="646ea-116">Procesos, vistas y administración de memoria</span><span class="sxs-lookup"><span data-stu-id="646ea-116">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="646ea-117">Los archivos asignados a memoria se pueden compartir entre varios procesos.</span><span class="sxs-lookup"><span data-stu-id="646ea-117">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="646ea-118">Los procesos pueden realizar una asignación al mismo archivo asignado a memoria usando un nombre común asignado por el proceso que creó el archivo.</span><span class="sxs-lookup"><span data-stu-id="646ea-118">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="646ea-119">Para trabajar con un archivo asignado a memoria, debe crear una vista de todo o parte del archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-119">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="646ea-120">También puede crear varias vistas a la misma parte del archivo asignado a memoria, creando de esta forma memoria simultánea.</span><span class="sxs-lookup"><span data-stu-id="646ea-120">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="646ea-121">Para que dos vistas sigan siendo simultáneas, tienen que crearse a partir del mismo archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-121">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="646ea-122">También puede ser necesario el uso de varias vistas si el archivo es mayor que el tamaño del espacio de memoria lógico de la aplicación disponible para la asignación de memoria (2 GB en un equipo de 32 bits).</span><span class="sxs-lookup"><span data-stu-id="646ea-122">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="646ea-123">Hay dos tipos de vista: vista de acceso secuencial y vista de acceso aleatorio.</span><span class="sxs-lookup"><span data-stu-id="646ea-123">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="646ea-124">Use las vistas de acceso secuencial para obtener acceso secuencial a un archivo; es la vista recomendada para los archivos no persistentes y las IPC.</span><span class="sxs-lookup"><span data-stu-id="646ea-124">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="646ea-125">Se recomiendan usar las vistas de acceso aleatorio para trabajar con archivos persistentes.</span><span class="sxs-lookup"><span data-stu-id="646ea-125">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="646ea-126">El acceso a los archivos asignados a memoria se realiza a través del administrador de memoria del sistema operativo, de modo que el archivo se divide automáticamente en varias páginas y el acceso se realizará según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="646ea-126">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="646ea-127">El usuario no tiene que encargarse de administrar la memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-127">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="646ea-128">En la siguiente ilustración se muestra cómo varios procesos pueden presentar simultáneamente varias vistas superpuestas del mismo archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-128">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>

 <span data-ttu-id="646ea-129">En la imagen siguiente se muestran varias vistas superpuestas de un archivo asignado a memoria:</span><span class="sxs-lookup"><span data-stu-id="646ea-129">The following image shows multiple and overlapped views to a memory-mapped file:</span></span>  
  
 ![Captura de pantalla que muestra las vistas de un archivo asignado a memoria.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="646ea-131">Programar con archivos asignados a memoria</span><span class="sxs-lookup"><span data-stu-id="646ea-131">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="646ea-132">En la siguiente tabla, se describe cómo usar los objetos de archivo asignado a memoria y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="646ea-132">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="646ea-133">Tarea</span><span class="sxs-lookup"><span data-stu-id="646ea-133">Task</span></span>|<span data-ttu-id="646ea-134">Métodos o propiedades que se usan</span><span class="sxs-lookup"><span data-stu-id="646ea-134">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="646ea-135">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria persistente de un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-135">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="646ea-136">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-136"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="646ea-137">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria no persistente (no asociado a ningún archivo en disco).</span><span class="sxs-lookup"><span data-stu-id="646ea-137">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="646ea-138">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-138"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="646ea-139">o bien</span><span class="sxs-lookup"><span data-stu-id="646ea-139">- or -</span></span><br /><br /> <span data-ttu-id="646ea-140">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-140"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="646ea-141">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> de un archivo asignado a memoria existente (persistente o no persistente).</span><span class="sxs-lookup"><span data-stu-id="646ea-141">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="646ea-142">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-142"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="646ea-143">Para obtener un objeto <xref:System.IO.UnmanagedMemoryStream> de una vista de acceso secuencial al archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-143">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="646ea-144">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-144"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="646ea-145">Para obtener un objeto <xref:System.IO.UnmanagedMemoryAccessor> de una vista de acceso aleatorio a un archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-145">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="646ea-146">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-146"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="646ea-147">Para obtener un objeto <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> que se va a usar con código no administrado.</span><span class="sxs-lookup"><span data-stu-id="646ea-147">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="646ea-148">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-148"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="646ea-149">o bien</span><span class="sxs-lookup"><span data-stu-id="646ea-149">- or -</span></span><br /><br /> <span data-ttu-id="646ea-150">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-150"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="646ea-151">o bien</span><span class="sxs-lookup"><span data-stu-id="646ea-151">- or -</span></span><br /><br /> <span data-ttu-id="646ea-152">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-152"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="646ea-153">Para retrasar la asignación de memoria hasta que se crea una vista (solo archivos no persistentes).</span><span class="sxs-lookup"><span data-stu-id="646ea-153">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="646ea-154">(Para determinar el actual tamaño de página del sistema, utilice la propiedad <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="646ea-154">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="646ea-155">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> con el valor <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="646ea-155"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="646ea-156">o bien</span><span class="sxs-lookup"><span data-stu-id="646ea-156">- or -</span></span><br /><br /> <span data-ttu-id="646ea-157">Métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="646ea-157"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="646ea-158">Seguridad</span><span class="sxs-lookup"><span data-stu-id="646ea-158">Security</span></span>  
 <span data-ttu-id="646ea-159">Se pueden aplicar derechos de acceso cuando se crea un archivo asignado a memoria si se usan los siguientes métodos con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> como parámetro:</span><span class="sxs-lookup"><span data-stu-id="646ea-159">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="646ea-160">Se pueden especificar derechos de acceso para abrir un archivo asignado a memoria existente si se usan los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="646ea-160">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="646ea-161">Además, se puede incluir un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>, que contiene reglas de acceso predefinidas.</span><span class="sxs-lookup"><span data-stu-id="646ea-161">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="646ea-162">Para aplicar reglas de acceso nuevas o modificadas a un archivo asignado a memoria, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="646ea-162">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="646ea-163">Para recuperar las reglas de acceso o de auditoría de un archivo existente, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="646ea-163">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="646ea-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="646ea-164">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="646ea-165">Archivos asignados a memoria persistentes</span><span class="sxs-lookup"><span data-stu-id="646ea-165">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="646ea-166">Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> crean un archivo asignado a memoria a partir de un archivo existente en disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-166">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="646ea-167">En el ejemplo siguiente se crea una vista asignada a memoria de una parte de un archivo muy grande y se manipula una parte de él.</span><span class="sxs-lookup"><span data-stu-id="646ea-167">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 <span data-ttu-id="646ea-168">En el siguiente ejemplo, se abre el mismo archivo asignado a memoria para otro proceso.</span><span class="sxs-lookup"><span data-stu-id="646ea-168">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="646ea-169">Archivos asignados a memoria no persistentes</span><span class="sxs-lookup"><span data-stu-id="646ea-169">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="646ea-170">Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> y <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> crean un archivo asignado a memoria que no está asignado a un archivo existente en el disco.</span><span class="sxs-lookup"><span data-stu-id="646ea-170">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="646ea-171">El ejemplo siguiente consta de tres procesos independientes (aplicaciones de consola) que escriben valores booleanos en un archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-171">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="646ea-172">Se produce la siguiente secuencia de acciones:</span><span class="sxs-lookup"><span data-stu-id="646ea-172">The following sequence of actions occur:</span></span>  
  
1. <span data-ttu-id="646ea-173">`Process A` crea el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="646ea-173">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2. <span data-ttu-id="646ea-174">`Process B` abre el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="646ea-174">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3. <span data-ttu-id="646ea-175">`Process C` abre el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="646ea-175">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4. <span data-ttu-id="646ea-176">`Process A` lee y muestra los valores del archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="646ea-176">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5. <span data-ttu-id="646ea-177">Una vez que `Process A` termina con el archivo asignado a memoria, la recolección de elementos no utilizados recupera el archivo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="646ea-177">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="646ea-178">Para ejecutar este ejemplo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="646ea-178">To run this example, do the following:</span></span>  
  
1. <span data-ttu-id="646ea-179">Compile las aplicaciones y abra tres ventanas de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="646ea-179">Compile the applications and open three Command Prompt windows.</span></span>  
  
2. <span data-ttu-id="646ea-180">En la primera ventana de símbolo del sistema, ejecute `Process A`.</span><span class="sxs-lookup"><span data-stu-id="646ea-180">In the first Command Prompt window, run `Process A`.</span></span>  
  
3. <span data-ttu-id="646ea-181">En la segunda ventana de símbolo del sistema, ejecute `Process B`.</span><span class="sxs-lookup"><span data-stu-id="646ea-181">In the second Command Prompt window, run `Process B`.</span></span>  
  
4. <span data-ttu-id="646ea-182">Vuelva a `Process A` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="646ea-182">Return to `Process A` and press ENTER.</span></span>  
  
5. <span data-ttu-id="646ea-183">En la tercera ventana de símbolo del sistema, ejecute `Process C`.</span><span class="sxs-lookup"><span data-stu-id="646ea-183">In the third Command Prompt window, run `Process C`.</span></span>  
  
6. <span data-ttu-id="646ea-184">Vuelva a `Process A` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="646ea-184">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="646ea-185">La salida de `Process A` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="646ea-185">The output of `Process A` is as follows:</span></span>  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="646ea-186">**Process A**</span><span class="sxs-lookup"><span data-stu-id="646ea-186">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="646ea-187">**Process B**</span><span class="sxs-lookup"><span data-stu-id="646ea-187">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="646ea-188">**Process C**</span><span class="sxs-lookup"><span data-stu-id="646ea-188">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="646ea-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="646ea-189">See also</span></span>

- [<span data-ttu-id="646ea-190">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="646ea-190">File and Stream I/O</span></span>](index.md)
