---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606896"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="df43f-101">SqlConnection ya no se puede conectar a SQL Server 1997 o a bases de datos mediante el adaptador VIA</span><span class="sxs-lookup"><span data-stu-id="df43f-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="df43f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="df43f-102">Details</span></span>

<span data-ttu-id="df43f-103">Ya no se admiten las conexiones a las bases de datos de SQL Server mediante el [protocolo Adaptador de interfaz virtual (VIA)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)).</span><span class="sxs-lookup"><span data-stu-id="df43f-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="df43f-104">El protocolo que se usa para conectarse a una base de datos de SQL Server es visible en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="df43f-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="df43f-105">Una conexión de VIA contendrá via:&lt;nombre_de_servidor&gt;.</span><span class="sxs-lookup"><span data-stu-id="df43f-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="df43f-106">Si esta aplicación se conecta a SQL a través de un protocolo distinto de VIA (tcp: o np: por ejemplo), no se encontrará ningún cambio importante.</span><span class="sxs-lookup"><span data-stu-id="df43f-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="df43f-107">Además, ya no se admiten las conexiones a SQL Server 7 (1997).</span><span class="sxs-lookup"><span data-stu-id="df43f-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df43f-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="df43f-108">Suggestion</span></span>

<span data-ttu-id="df43f-109">El protocolo VIA está en desuso, por lo que se debe usar un protocolo alternativo para conectarse a las bases de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="df43f-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="df43f-110">El protocolo que más se usa es TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="df43f-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="df43f-111">Para más información sobre cómo conectarse a través de TCP/IP, consulte el artículo sobre cómo [habilitar el protocolo TCP/IP para una instancia de base de datos](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="df43f-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="df43f-112">Si solo se tiene acceso a la base de datos desde dentro de una intranet, el protocolo de canalizaciones compartidas puede proporcionar un mejor rendimiento si la red es lenta.</span><span class="sxs-lookup"><span data-stu-id="df43f-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="df43f-113">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="df43f-113">Name</span></span>    | <span data-ttu-id="df43f-114">Valor</span><span class="sxs-lookup"><span data-stu-id="df43f-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df43f-115">Ámbito</span><span class="sxs-lookup"><span data-stu-id="df43f-115">Scope</span></span>   |<span data-ttu-id="df43f-116">Borde</span><span class="sxs-lookup"><span data-stu-id="df43f-116">Edge</span></span>|
|<span data-ttu-id="df43f-117">Versión</span><span class="sxs-lookup"><span data-stu-id="df43f-117">Version</span></span>|<span data-ttu-id="df43f-118">4.5</span><span class="sxs-lookup"><span data-stu-id="df43f-118">4.5</span></span>|
|<span data-ttu-id="df43f-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="df43f-119">Type</span></span>|<span data-ttu-id="df43f-120">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="df43f-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="df43f-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="df43f-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
