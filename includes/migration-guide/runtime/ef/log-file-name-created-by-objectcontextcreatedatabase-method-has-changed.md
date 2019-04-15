---
ms.openlocfilehash: cf1a8169351e29c18d85303fb32d4394877448f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235962"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="c36d8-101">El nombre de archivo de registro creado por el método ObjectContext.CreateDatabase ha cambiado para coincidir con las especificaciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c36d8-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c36d8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c36d8-102">Details</span></span>|<span data-ttu-id="c36d8-103">Cuando se llama al método <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> directamente o mediante Code First con el proveedor SqlClient y un valor AttachDBFilename en la cadena de conexión, se crea un archivo de registro denominado nombreDeArchivo_log.ldf en lugar de nombreDeArchivo.ldf (donde nombreDeArchivo es el nombre del archivo especificado mediante el valor AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="c36d8-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="c36d8-104">Este cambio mejora la depuración al proporcionar un archivo de registro cuyo nombre se ajusta a las especificaciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c36d8-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>|
|<span data-ttu-id="c36d8-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c36d8-105">Suggestion</span></span>|<span data-ttu-id="c36d8-106">Si el nombre de archivo de registro es importante para una aplicación, la aplicación debería actualizarse para que espere el formato de nombre de archivo estándar _log.ldf.</span><span class="sxs-lookup"><span data-stu-id="c36d8-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>|
|<span data-ttu-id="c36d8-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c36d8-107">Scope</span></span>|<span data-ttu-id="c36d8-108">Borde</span><span class="sxs-lookup"><span data-stu-id="c36d8-108">Edge</span></span>|
|<span data-ttu-id="c36d8-109">Versión</span><span class="sxs-lookup"><span data-stu-id="c36d8-109">Version</span></span>|<span data-ttu-id="c36d8-110">4.5</span><span class="sxs-lookup"><span data-stu-id="c36d8-110">4.5</span></span>|
|<span data-ttu-id="c36d8-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="c36d8-111">Type</span></span>|<span data-ttu-id="c36d8-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c36d8-112">Runtime</span></span>|
|<span data-ttu-id="c36d8-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c36d8-113">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
