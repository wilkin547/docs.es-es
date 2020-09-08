---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497249"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="269c0-101">ADO.NET ahora intenta volver a conectar automáticamente las conexiones SQL interrumpidas</span><span class="sxs-lookup"><span data-stu-id="269c0-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="269c0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="269c0-102">Details</span></span>

<span data-ttu-id="269c0-103">A partir de la versión 4.5.1, .NET Framework intentará volver a conectar automáticamente las conexiones SQL interrumpidas.</span><span class="sxs-lookup"><span data-stu-id="269c0-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="269c0-104">Aunque por lo general esto hará que las aplicaciones sean más confiables, hay casos extremos en los que la aplicación tiene que saber que se perdió la conexión para poder realizar alguna acción al volverse a conectar.</span><span class="sxs-lookup"><span data-stu-id="269c0-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="269c0-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="269c0-105">Suggestion</span></span>

<span data-ttu-id="269c0-106">Si por motivos de compatibilidad no quiere esta característica, se puede deshabilitar estableciendo la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> de una cadena de conexión (o <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) en 0.</span><span class="sxs-lookup"><span data-stu-id="269c0-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="269c0-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="269c0-107">Name</span></span>    | <span data-ttu-id="269c0-108">Valor</span><span class="sxs-lookup"><span data-stu-id="269c0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="269c0-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="269c0-109">Scope</span></span>   |<span data-ttu-id="269c0-110">Borde</span><span class="sxs-lookup"><span data-stu-id="269c0-110">Edge</span></span>|
|<span data-ttu-id="269c0-111">Versión</span><span class="sxs-lookup"><span data-stu-id="269c0-111">Version</span></span>|<span data-ttu-id="269c0-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="269c0-112">4.5.1</span></span>|
|<span data-ttu-id="269c0-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="269c0-113">Type</span></span>|<span data-ttu-id="269c0-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="269c0-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="269c0-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="269c0-115">Affected APIs</span></span>

- <xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)>

<!--

#### Affected APIs

- `P:System.Data.IDbConnection.ConnectionString`
- `P:System.Data.SqlClient.SqlConnection.ConnectionString`
- `P:System.Configuration.ConnectionStringSettings.ConnectionString`
- `P:System.Data.Common.DbConnection.ConnectionString`
- `P:System.Data.Common.DbConnectionStringBuilder.ConnectionString`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor(System.String)`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor(System.Boolean)`

-->
