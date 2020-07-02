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
# <a name="memory-mapped-files"></a>Archivos asignados a memoria
Un archivo asignado a memoria incluye el contenido de un archivo en la memoria virtual. Esta asignación entre un archivo y el espacio de memoria permite a una aplicación, incluidos varios procesos, modificar el archivo leyendo y escribiendo directamente en la memoria. A partir de .NET Framework 4, se puede usar código administrado para tener acceso a los archivos asignados a memoria del mismo modo que las funciones nativas de Windows tienen acceso a los archivos asignados a memoria, tal como se describe en [Administración de archivos asignados a memoria](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)).  
  
 Hay dos tipos de archivos asignados a memoria:  
  
- Archivos asignados a memoria persistentes  
  
     Los archivos persistentes son archivos asignados a memoria que están asociados a un archivo de origen ubicado en un disco. Cuando el último proceso termina de usar el archivo, los datos se guardan en el archivo de origen ubicado en el disco. Estos archivos asignados a memoria son idóneos para trabajar con archivos de origen muy grandes.  
  
- Archivos asignados a memoria no persistentes  
  
     Los archivos no persistentes son archivos asignados a memoria que no están asociados a un archivo ubicado en un disco. Cuando el último proceso termina de usar el archivo, se pierden los datos y la recolección de elementos no utilizados reclama el archivo. Estos archivos son idóneos para crear memoria compartida para las comunicaciones entre procesos (IPC).  
  
## <a name="processes-views-and-managing-memory"></a>Procesos, vistas y administración de memoria  
 Los archivos asignados a memoria se pueden compartir entre varios procesos. Los procesos pueden realizar una asignación al mismo archivo asignado a memoria usando un nombre común asignado por el proceso que creó el archivo.  
  
 Para trabajar con un archivo asignado a memoria, debe crear una vista de todo o parte del archivo asignado a memoria. También puede crear varias vistas a la misma parte del archivo asignado a memoria, creando de esta forma memoria simultánea. Para que dos vistas sigan siendo simultáneas, tienen que crearse a partir del mismo archivo asignado a memoria.  
  
 También puede ser necesario el uso de varias vistas si el archivo es mayor que el tamaño del espacio de memoria lógico de la aplicación disponible para la asignación de memoria (2 GB en un equipo de 32 bits).  
  
 Hay dos tipos de vista: vista de acceso secuencial y vista de acceso aleatorio. Use las vistas de acceso secuencial para obtener acceso secuencial a un archivo; es la vista recomendada para los archivos no persistentes y las IPC. Se recomiendan usar las vistas de acceso aleatorio para trabajar con archivos persistentes.  
  
 El acceso a los archivos asignados a memoria se realiza a través del administrador de memoria del sistema operativo, de modo que el archivo se divide automáticamente en varias páginas y el acceso se realizará según sea necesario. El usuario no tiene que encargarse de administrar la memoria.  
  
 En la siguiente ilustración se muestra cómo varios procesos pueden presentar simultáneamente varias vistas superpuestas del mismo archivo asignado a memoria.

 En la imagen siguiente se muestran varias vistas superpuestas de un archivo asignado a memoria:  
  
 ![Captura de pantalla que muestra las vistas de un archivo asignado a memoria.](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a>Programar con archivos asignados a memoria  
 En la siguiente tabla, se describe cómo usar los objetos de archivo asignado a memoria y sus miembros.  
  
|Tarea|Métodos o propiedades que se usan|  
|----------|----------------------------------|  
|Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria persistente de un archivo en disco.|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>.|  
|Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> que representa un archivo asignado a memoria no persistente (no asociado a ningún archivo en disco).|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>.<br /><br /> o bien<br /><br /> Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>.|  
|Para obtener un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> de un archivo asignado a memoria existente (persistente o no persistente).|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType>.|  
|Para obtener un objeto <xref:System.IO.UnmanagedMemoryStream> de una vista de acceso secuencial al archivo asignado a memoria.|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType>.|  
|Para obtener un objeto <xref:System.IO.UnmanagedMemoryAccessor> de una vista de acceso aleatorio a un archivo asignado a memoria.|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType>.|  
|Para obtener un objeto <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> que se va a usar con código no administrado.|Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>.<br /><br /> o bien<br /><br /> Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.<br /><br /> o bien<br /><br /> Propiedad <xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>.|  
|Para retrasar la asignación de memoria hasta que se crea una vista (solo archivos no persistentes).<br /><br /> (Para determinar el actual tamaño de página del sistema, utilice la propiedad <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>.)|Método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> con el valor <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>.<br /><br /> o bien<br /><br /> Métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> como parámetro.|  
  
### <a name="security"></a>Seguridad  
 Se pueden aplicar derechos de acceso cuando se crea un archivo asignado a memoria si se usan los siguientes métodos con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> como parámetro:  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 Se pueden especificar derechos de acceso para abrir un archivo asignado a memoria existente si se usan los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> con la enumeración <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> como parámetro.  
  
 Además, se puede incluir un objeto <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>, que contiene reglas de acceso predefinidas.  
  
 Para aplicar reglas de acceso nuevas o modificadas a un archivo asignado a memoria, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>. Para recuperar las reglas de acceso o de auditoría de un archivo existente, utilice el método <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="persisted-memory-mapped-files"></a>Archivos asignados a memoria persistentes  
 Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> crean un archivo asignado a memoria a partir de un archivo existente en disco.  
  
 En el ejemplo siguiente se crea una vista asignada a memoria de una parte de un archivo muy grande y se manipula una parte de él.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 En el siguiente ejemplo, se abre el mismo archivo asignado a memoria para otro proceso.  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a>Archivos asignados a memoria no persistentes  
 Los métodos <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> y <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> crean un archivo asignado a memoria que no está asignado a un archivo existente en el disco.  
  
 El ejemplo siguiente consta de tres procesos independientes (aplicaciones de consola) que escriben valores booleanos en un archivo asignado a memoria. Se produce la siguiente secuencia de acciones:  
  
1. `Process A` crea el archivo asignado a memoria y escribe un valor en él.  
  
2. `Process B` abre el archivo asignado a memoria y escribe un valor en él.  
  
3. `Process C` abre el archivo asignado a memoria y escribe un valor en él.  
  
4. `Process A` lee y muestra los valores del archivo asignado a memoria.  
  
5. Una vez que `Process A` termina con el archivo asignado a memoria, la recolección de elementos no utilizados recupera el archivo inmediatamente.  
  
 Para ejecutar este ejemplo, haga lo siguiente:  
  
1. Compile las aplicaciones y abra tres ventanas de símbolo del sistema.  
  
2. En la primera ventana de símbolo del sistema, ejecute `Process A`.  
  
3. En la segunda ventana de símbolo del sistema, ejecute `Process B`.  
  
4. Vuelva a `Process A` y presione ENTRAR.  
  
5. En la tercera ventana de símbolo del sistema, ejecute `Process C`.  
  
6. Vuelva a `Process A` y presione ENTRAR.  
  
 La salida de `Process A` es la siguiente:  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 **Process A**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 **Process B**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 **Process C**  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [E/S de archivos y secuencias](index.md)
