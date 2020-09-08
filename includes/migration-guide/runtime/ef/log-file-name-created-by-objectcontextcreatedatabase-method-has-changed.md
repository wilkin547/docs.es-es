---
ms.openlocfilehash: e77e37156de759856c8a6f2e0c009caf9e1fe826
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497742"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="66be8-101">El nombre de archivo de registro creado por el método ObjectContext.CreateDatabase ha cambiado para coincidir con las especificaciones de SQL Server</span><span class="sxs-lookup"><span data-stu-id="66be8-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="66be8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="66be8-102">Details</span></span>

<span data-ttu-id="66be8-103">Cuando se llama al método <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> directamente o mediante Code First con el proveedor SqlClient y un valor AttachDBFilename en la cadena de conexión, se crea un archivo de registro denominado nombreDeArchivo_log.ldf en lugar de nombreDeArchivo.ldf (donde nombreDeArchivo es el nombre del archivo especificado mediante el valor AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="66be8-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="66be8-104">Este cambio mejora la depuración al proporcionar un archivo de registro cuyo nombre se ajusta a las especificaciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66be8-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="66be8-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="66be8-105">Suggestion</span></span>

<span data-ttu-id="66be8-106">Si el nombre de archivo de registro es importante para una aplicación, la aplicación debería actualizarse para que espere el formato de nombre de archivo estándar _log.ldf.</span><span class="sxs-lookup"><span data-stu-id="66be8-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="66be8-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="66be8-107">Name</span></span>    | <span data-ttu-id="66be8-108">Valor</span><span class="sxs-lookup"><span data-stu-id="66be8-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="66be8-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="66be8-109">Scope</span></span>   |<span data-ttu-id="66be8-110">Borde</span><span class="sxs-lookup"><span data-stu-id="66be8-110">Edge</span></span>|
|<span data-ttu-id="66be8-111">Versión</span><span class="sxs-lookup"><span data-stu-id="66be8-111">Version</span></span>|<span data-ttu-id="66be8-112">4.5</span><span class="sxs-lookup"><span data-stu-id="66be8-112">4.5</span></span>|
|<span data-ttu-id="66be8-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="66be8-113">Type</span></span>|<span data-ttu-id="66be8-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="66be8-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="66be8-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="66be8-115">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`

-->
