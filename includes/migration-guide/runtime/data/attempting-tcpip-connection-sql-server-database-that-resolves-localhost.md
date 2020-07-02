---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621819"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="e9c20-101">No se puede intentar una conexión TCP/IP a una base de datos de SQL Server que se resuelve en `localhost`</span><span class="sxs-lookup"><span data-stu-id="e9c20-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="e9c20-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e9c20-102">Details</span></span>

<span data-ttu-id="e9c20-103">En .NET Framework 4.6 y 4.6.1, el intento de una conexión TCP/IP a una base de datos de SQL Server que se resuelve en <code>localhost</code> produce el error &quot;Error relacionado con la red o específico de la instancia mientras se establecía una conexión con el servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9c20-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="e9c20-104">No se encontró el servidor o éste no estaba accesible.</span><span class="sxs-lookup"><span data-stu-id="e9c20-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="e9c20-105">Compruebe que el nombre de la instancia es correcto y que SQL Server está configurado para admitir conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="e9c20-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="e9c20-106">(proveedor: Interfaces de red SQL, error: 26: Error al buscar el servidor/instancia especificado)&quot;</span><span class="sxs-lookup"><span data-stu-id="e9c20-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e9c20-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e9c20-107">Suggestion</span></span>

<span data-ttu-id="e9c20-108">Este problema se ha resuelto y se ha restaurado el comportamiento anterior, en .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e9c20-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="e9c20-109">Para conectarse a una base de datos de SQL Server que se resuelve en <code>localhost</code>, actualice a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="e9c20-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="e9c20-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e9c20-110">Name</span></span>    | <span data-ttu-id="e9c20-111">Valor</span><span class="sxs-lookup"><span data-stu-id="e9c20-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e9c20-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e9c20-112">Scope</span></span>   |<span data-ttu-id="e9c20-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="e9c20-113">Minor</span></span>|
|<span data-ttu-id="e9c20-114">Versión</span><span class="sxs-lookup"><span data-stu-id="e9c20-114">Version</span></span>|<span data-ttu-id="e9c20-115">4.6</span><span class="sxs-lookup"><span data-stu-id="e9c20-115">4.6</span></span>|
|<span data-ttu-id="e9c20-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9c20-116">Type</span></span>|<span data-ttu-id="e9c20-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e9c20-117">Runtime</span></span>|
