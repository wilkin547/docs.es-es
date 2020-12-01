---
title: Archivos asignados a memoria
description: Explore los archivos asignados a memoria en .NET, que mantienen el contenido de los archivos en la memoria virtual, y permita que las aplicaciones modifiquen el archivo escribiendo directamente en la memoria.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
ms.openlocfilehash: 4a179bff7ec7988c5b7410fa99eab346d4add1df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734834"
---
# <a name="memory-mapped-files"></a><span data-ttu-id="fa91a-103">Archivos asignados a memoria</span><span class="sxs-lookup"><span data-stu-id="fa91a-103">Memory-mapped files</span></span>

<span data-ttu-id="fa91a-104">Un archivo asignado a memoria incluye el contenido de un archivo en la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="fa91a-104">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="fa91a-105">Esta asignación entre un archivo y el espacio de memoria permite a una aplicación, incluidos varios procesos, modificar el archivo leyendo y escribiendo directamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-105">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="fa91a-106">Puede usar código administrado para acceder a los archivos asignados a memoria del mismo modo que las funciones nativas de Windows acceden a los archivos asignados a memoria, como se describe en [Administración de archivos asignados a memoria](/previous-versions/ms810613(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="fa91a-106">You can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](/previous-versions/ms810613(v=msdn.10)).</span></span>  
  
<span data-ttu-id="fa91a-107">Hay dos tipos de archivos asignados a memoria:</span><span class="sxs-lookup"><span data-stu-id="fa91a-107">There are two types of memory-mapped files:</span></span>  
  
- <span data-ttu-id="fa91a-108">Archivos asignados a memoria persistentes</span><span class="sxs-lookup"><span data-stu-id="fa91a-108">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="fa91a-109">Los archivos persistentes son archivos asignados a memoria que están asociados a un archivo de origen ubicado en un disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-109">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="fa91a-110">Cuando el último proceso termina de usar el archivo, los datos se guardan en el archivo de origen ubicado en el disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-110">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="fa91a-111">Estos archivos asignados a memoria son idóneos para trabajar con archivos de origen muy grandes.</span><span class="sxs-lookup"><span data-stu-id="fa91a-111">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
- <span data-ttu-id="fa91a-112">Archivos asignados a memoria no persistentes</span><span class="sxs-lookup"><span data-stu-id="fa91a-112">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="fa91a-113">Los archivos no persistentes son archivos asignados a memoria que no están asociados a un archivo ubicado en un disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-113">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="fa91a-114">Cuando el último proceso termina de usar el archivo, se pierden los datos y la recolección de elementos no utilizados reclama el archivo.</span><span class="sxs-lookup"><span data-stu-id="fa91a-114">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="fa91a-115">Estos archivos son idóneos para crear memoria compartida para las comunicaciones entre procesos (IPC).</span><span class="sxs-lookup"><span data-stu-id="fa91a-115">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="fa91a-116">Procesos, vistas y administración de memoria</span><span class="sxs-lookup"><span data-stu-id="fa91a-116">Processes, Views, and Managing Memory</span></span>  

 <span data-ttu-id="fa91a-117">Los archivos asignados a memoria se pueden compartir entre varios procesos.</span><span class="sxs-lookup"><span data-stu-id="fa91a-117">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="fa91a-118">Los procesos pueden realizar una asignación al mismo archivo asignado a memoria usando un nombre común asignado por el proceso que creó el archivo.</span><span class="sxs-lookup"><span data-stu-id="fa91a-118">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="fa91a-119">Para trabajar con un archivo asignado a memoria, debe crear una vista de todo o parte del archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-119">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="fa91a-120">También puede crear varias vistas a la misma parte del archivo asignado a memoria, creando de esta forma memoria simultánea.</span><span class="sxs-lookup"><span data-stu-id="fa91a-120">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="fa91a-121">Para que dos vistas sigan siendo simultáneas, tienen que crearse a partir del mismo archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-121">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="fa91a-122">También puede ser necesario usar varias vistas si el archivo tiene un tamaño mayor que el espacio de memoria lógico de la aplicación disponible para la asignación de memoria (2 GB en un equipo de 32 bits).</span><span class="sxs-lookup"><span data-stu-id="fa91a-122">Multiple views may also be necessary if the file is greater than the size of the application's logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="fa91a-123">Hay dos tipos de vista: vista de acceso secuencial y vista de acceso aleatorio.</span><span class="sxs-lookup"><span data-stu-id="fa91a-123">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="fa91a-124">Use las vistas de acceso secuencial para obtener acceso secuencial a un archivo; es la vista recomendada para los archivos no persistentes y las IPC.</span><span class="sxs-lookup"><span data-stu-id="fa91a-124">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="fa91a-125">Se recomiendan usar las vistas de acceso aleatorio para trabajar con archivos persistentes.</span><span class="sxs-lookup"><span data-stu-id="fa91a-125">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="fa91a-126">El acceso a los archivos asignados a memoria se realiza a través del administrador de memoria del sistema operativo, de modo que el archivo se divide automáticamente en varias páginas y el acceso se realiza según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fa91a-126">Memory-mapped files are accessed through the operating system's memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="fa91a-127">El usuario no tiene que encargarse de administrar la memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-127">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="fa91a-128">En la siguiente ilustración se muestra cómo varios procesos pueden presentar simultáneamente varias vistas superpuestas del mismo archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-128">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>

 <span data-ttu-id="fa91a-129">En la imagen siguiente se muestran varias vistas superpuestas de un archivo asignado a memoria:</span><span class="sxs-lookup"><span data-stu-id="fa91a-129">The following image shows multiple and overlapped views to a memory-mapped file:</span></span>  
  
 ![Captura de pantalla que muestra las vistas de un archivo asignado a memoria.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="fa91a-131">Programar con archivos asignados a memoria</span><span class="sxs-lookup"><span data-stu-id="fa91a-131">Programming with Memory-Mapped Files</span></span>  

 <span data-ttu-id="fa91a-132">En la siguiente tabla, se describe cómo usar los objetos de archivo asignado a memoria y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="fa91a-132">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="fa91a-133">Tarea</span><span class="sxs-lookup"><span data-stu-id="fa91a-133">Task</span></span>|<span data-ttu-id="fa91a-134">Métodos o propiedades que se usan</span><span class="sxs-lookup"><span data-stu-id="fa91a-134">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="fa91a-135">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria persistente de un archivo en disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-135">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="fa91a-136">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-136"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="fa91a-137">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria no persistente (no asociado a ningún archivo en disco).</span><span class="sxs-lookup"><span data-stu-id="fa91a-137">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="fa91a-138">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-138"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="fa91a-139">o bien</span><span class="sxs-lookup"><span data-stu-id="fa91a-139">- or -</span></span><br /><br /> <span data-ttu-id="fa91a-140">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-140"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="fa91a-141">Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> de un archivo asignado a memoria existente (persistente o no persistente).</span><span class="sxs-lookup"><span data-stu-id="fa91a-141">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="fa91a-142">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-142"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="fa91a-143">Para obtener un objeto <xref:System.IO.UnmanagedMemoryStream> de una vista de acceso secuencial al archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-143">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="fa91a-144">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-144"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="fa91a-145">Para obtener un objeto <xref:System.IO.UnmanagedMemoryAccessor> de una vista de acceso aleatorio a un archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-145">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="fa91a-146">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-146"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="fa91a-147">Para obtener un objeto <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> que se va a usar con código no administrado.</span><span class="sxs-lookup"><span data-stu-id="fa91a-147">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="fa91a-148">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-148"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="fa91a-149">o bien</span><span class="sxs-lookup"><span data-stu-id="fa91a-149">- or -</span></span><br /><br /> <span data-ttu-id="fa91a-150">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-150"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="fa91a-151">o bien</span><span class="sxs-lookup"><span data-stu-id="fa91a-151">- or -</span></span><br /><br /> <span data-ttu-id="fa91a-152">Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-152"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="fa91a-153">Para retrasar la asignación de memoria hasta que se crea una vista (solo archivos no persistentes).</span><span class="sxs-lookup"><span data-stu-id="fa91a-153">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="fa91a-154">(Para determinar el actual tamaño de página del sistema, utilice la propiedad <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="fa91a-154">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="fa91a-155">Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> con el valor <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-155"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="fa91a-156">o bien</span><span class="sxs-lookup"><span data-stu-id="fa91a-156">- or -</span></span><br /><br /> <span data-ttu-id="fa91a-157">Métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa91a-157"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="fa91a-158">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fa91a-158">Security</span></span>  

 <span data-ttu-id="fa91a-159">Se pueden aplicar derechos de acceso cuando se crea un archivo asignado a memoria si se usan los siguientes métodos con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> como parámetro:</span><span class="sxs-lookup"><span data-stu-id="fa91a-159">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="fa91a-160">Se pueden especificar derechos de acceso para abrir un archivo asignado a memoria existente si se usan los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa91a-160">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="fa91a-161">Además, se puede incluir un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>, que contiene reglas de acceso predefinidas.</span><span class="sxs-lookup"><span data-stu-id="fa91a-161">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="fa91a-162">Para aplicar reglas de acceso nuevas o modificadas a un archivo asignado a memoria, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-162">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="fa91a-163">Para recuperar las reglas de acceso o de auditoría de un archivo existente, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa91a-163">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fa91a-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fa91a-164">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="fa91a-165">Archivos asignados a memoria persistentes</span><span class="sxs-lookup"><span data-stu-id="fa91a-165">Persisted Memory-Mapped Files</span></span>  

 <span data-ttu-id="fa91a-166">Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> crean un archivo asignado a memoria a partir de un archivo existente en disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-166">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="fa91a-167">En el ejemplo siguiente se crea una vista asignada a memoria de una parte de un archivo muy grande y se manipula una parte de él.</span><span class="sxs-lookup"><span data-stu-id="fa91a-167">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 <span data-ttu-id="fa91a-168">En el siguiente ejemplo, se abre el mismo archivo asignado a memoria para otro proceso.</span><span class="sxs-lookup"><span data-stu-id="fa91a-168">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="fa91a-169">Archivos asignados a memoria no persistentes</span><span class="sxs-lookup"><span data-stu-id="fa91a-169">Non-Persisted Memory-Mapped Files</span></span>  

 <span data-ttu-id="fa91a-170">Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> y <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> crean un archivo asignado a memoria que no está asignado a un archivo existente en el disco.</span><span class="sxs-lookup"><span data-stu-id="fa91a-170">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="fa91a-171">El ejemplo siguiente consta de tres procesos independientes (aplicaciones de consola) que escriben valores booleanos en un archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-171">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="fa91a-172">Se produce la siguiente secuencia de acciones:</span><span class="sxs-lookup"><span data-stu-id="fa91a-172">The following sequence of actions occur:</span></span>  
  
1. <span data-ttu-id="fa91a-173">`Process A` crea el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="fa91a-173">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2. <span data-ttu-id="fa91a-174">`Process B` abre el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="fa91a-174">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3. <span data-ttu-id="fa91a-175">`Process C` abre el archivo asignado a memoria y escribe un valor en él.</span><span class="sxs-lookup"><span data-stu-id="fa91a-175">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4. <span data-ttu-id="fa91a-176">`Process A` lee y muestra los valores del archivo asignado a memoria.</span><span class="sxs-lookup"><span data-stu-id="fa91a-176">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5. <span data-ttu-id="fa91a-177">Una vez que `Process A` termina con el archivo asignado a memoria, la recolección de elementos no utilizados recupera el archivo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fa91a-177">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="fa91a-178">Para ejecutar este ejemplo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa91a-178">To run this example, do the following:</span></span>  
  
1. <span data-ttu-id="fa91a-179">Compile las aplicaciones y abra tres ventanas de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa91a-179">Compile the applications and open three Command Prompt windows.</span></span>  
  
2. <span data-ttu-id="fa91a-180">En la primera ventana de símbolo del sistema, ejecute `Process A`.</span><span class="sxs-lookup"><span data-stu-id="fa91a-180">In the first Command Prompt window, run `Process A`.</span></span>  
  
3. <span data-ttu-id="fa91a-181">En la segunda ventana de símbolo del sistema, ejecute `Process B`.</span><span class="sxs-lookup"><span data-stu-id="fa91a-181">In the second Command Prompt window, run `Process B`.</span></span>  
  
4. <span data-ttu-id="fa91a-182">Vuelva a `Process A` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fa91a-182">Return to `Process A` and press ENTER.</span></span>  
  
5. <span data-ttu-id="fa91a-183">En la tercera ventana de símbolo del sistema, ejecute `Process C`.</span><span class="sxs-lookup"><span data-stu-id="fa91a-183">In the third Command Prompt window, run `Process C`.</span></span>  
  
6. <span data-ttu-id="fa91a-184">Vuelva a `Process A` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fa91a-184">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="fa91a-185">La salida de `Process A` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa91a-185">The output of `Process A` is as follows:</span></span>  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="fa91a-186">**Process A**</span><span class="sxs-lookup"><span data-stu-id="fa91a-186">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="fa91a-187">**Process B**</span><span class="sxs-lookup"><span data-stu-id="fa91a-187">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="fa91a-188">**Process C**</span><span class="sxs-lookup"><span data-stu-id="fa91a-188">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fa91a-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa91a-189">See also</span></span>

- [<span data-ttu-id="fa91a-190">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="fa91a-190">File and Stream I/O</span></span>](index.md)
